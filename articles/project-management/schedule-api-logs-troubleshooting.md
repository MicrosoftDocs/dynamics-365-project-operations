---
title: Troubleshoot project scheduling errors in the task grid
description: Learn how to troubleshoot project scheduling errors that are related to the Project Scheduling Service and Project schedule APIs.
author: dishantpopli  
ms.date: 03/11/2025
ms.topic: troubleshooting
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli

---

# Troubleshoot project scheduling errors in the task grid

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

When you work in the task grid, changes to the work breakdown structure (WBS) sometimes aren't saved, and you receive the following error message:

> Recent change you've made couldn't be saved.

This article explains common causes of this error.

## Project task end/due date can't be earlier than task start date

After you update the project calendar, you receive a save error when you select the **Tasks** tab. The Project Scheduling Service (PSS) error log shows the following message:

> Project Task end/due date can't be earlier than task start date.

### Mitigation

Contact your administrator for help. To fix this issue, your administrator must run a script.

To run the script, your administrator follows these steps.

1. Select <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd> to open the Developer console.
1. Copy the following script, and paste it into the Developer console. Modify the script by adding the task IDs of the tasks that are causing the errors. You can find the task IDs in the PSS error log.

    ```JS
    const listOfTasks = ["TASK IDS HERE"];
    /*
    * @params: listOfTasks: List of Tasks to retrieve associated Resource Assignments
    * @returns: Returns an array of associated Resource Assignments
    */
    async function getResourceAssignmentsAssociatedWithListOfTasks(listOfTasks) {
        let distinctAssignments = new Set();
    
        for (let i = 0; i < listOfTasks.length; i++) {
            let fetchXml = `?fetchXml=<fetch mapping="logical">
                                <entity name="msdyn_resourceassignment">
                                    <attribute name="msdyn_resourceassignmentid" />
                                    <filter>
                                        <condition attribute="taskid" operator="eq" value="${listOfTasks[i]}" />
                                    </filter>
                                </entity>
                            </fetch>`;
    
            let results = await Xrm.WebApi.retrieveMultipleRecords('msdyn_resourceassignment', fetchXml);
    
            for (let j = 0; j < results.entities.length; j++){
                distinctAssignments.add(results.entities[j].msdyn_resourceassignmentid);
            }
        }
        return Array.from(distinctAssignments);
    }
    
    // Call the async function and log the results
    getResourceAssignmentsAssociatedWithListOfTasks(listOfTasks).then(assignments => {
        console.log(assignments);
    }).catch(error => {
        console.error(error);
    });
    ```

1. Run the script to get the list of resource assignments for the tasks that have errors.
1. Delete the resource assignments by using the [Delete schedule API](schedule-api-preview.md).

Deletion of the resource assignments enables the project to be opened correctly. You can then re-create the assignments.

## Revision token doesn't match between xRM and PSS

When you try to make changes in the task grid, the edits sometimes revert after a while, or you receive a save error. The PSS error log shows the following message:

> Revision Token doesn't match between xRM and PSS.

This issue can occur for the following reasons:

- A long save process timed out. After two hours, PSS times out and reverts the edits. However, because Microsoft Dataverse continues and completes the save, a revision mismatch occurs.
- The ReadMpp request returns empty for the revision token. This situation indicates either that the MPP file was deleted, or it wasn't created in Dataverse. As a result, all project data was lost.

### Mitigation
If deleting the existing project and creating a new one isn’t possible, please contact support.

## Entity doesn't contain attribute

After you update the project calendar, you receive a save error when you select the **Tasks** tab. The PSS error log shows the following message:

> \<*EntityName*\> entity doesn't contain attribute with Name = \<*AttributeName*\> and NameMapping = `Logical`

### Mitigation

This issue probably occurs because you use custom pricing dimensions, and a custom dimension isn't linked to the affected Project Service Pricing entity.

To fix this issue, follow the instructions in [Entity-based custom pricing dimensions](../pricing-costing/add-custom-fields-price-setup-transactional-entities.md#entity-based-custom-pricing-dimensions) to correctly add the custom dimension to all required pricing entities. Alternatively, remove the custom dimension.

## Unable to delete a task

When you try to delete a task from the **Tasks** tab, it reappears after a few minutes. You might also receive a save error and be unable to make any edits in the task grid.

### Mitigation 1

This issue can occur if the **Microsoft Project or Microsoft Portfolios** app user doesn't have the correct permissions, or if data is corrupted.

Contact your administrator for help. To fix this issue, your administrator should first try to assign the correct permissions to the **Microsoft Project or Microsoft Portfolios** app user.

To assign the permissions, your administrator follows these steps.

1. Sign in to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/).
1. Select the environment.
1. In the right pane, select all users.
1. Select the app users list.
1. Select **Microsoft Project/Microsoft Portfolios**, and then select **Edit security roles**.
1. Ensure that the **Project System** and **Project Operations System** security roles are selected.

### Mitigation 2

If the first mitigation approach doesn't work, the issue is probably caused by data corruption. In this case, contact Support.

## System job has an error

When you create new tasks, a save error message appears on the task grid after a while. In the list of system jobs, a successful instance of **Project Service Core - SaveProjectDataFromPCSAsynchronousV1** is followed by one or more failed instances for the same project, as shown in the following screenshot.

![Screenshot that shows a system job that has an error.](media/systemjobhaserror.png)

When you inspect the system job, the following error appears:

> Revision Token doesn't match between xRM and PSS.

The mitigation approach depends on the root cause of the issue.

### Mitigation 1

The issue can occur because the **Project Application** user doesn't have the **Project System** role. In this case, ask your administrator to assign the **Basic User** and **Project System** roles to the **Project Application** user. For Dynamics 365 Project Operations, your administrator should also assign the **Project Operations System** role.

### Mitigation 2

The issue can occur because the **Project Application** user isn't in the default business unit but was moved to a child business unit. In this case, ask your administrator to move the **Project Application** user back to the default business unit. It must be in the default business unit.

### Mitigation 3

The issue can occur because an organization that previously had a single business unit switched to having multiple business units. As a result, some optimization was broken. In this case, ask your administrator to apply the mitigation that is described in the [Revision token doesn't match between xRM and PSS](#revision-token-doesnt-match-between-xrm-and-pss) section of this article.

If the issue persists, contact Support.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
