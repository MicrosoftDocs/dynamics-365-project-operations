---
title: Use Project schedule APIs wtih Power Automate
description: This topic provides a sample Flow utilizing Project schedule APIs .
author: ruhercul
ms.date: 01/20/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Use Project schedule APIs wtih Power Automate

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This topic provides information about how to create a complete project plan by using Power Automate.

This topic also provides information about how to create an Operation Set and update an entity.

The steps in the flow are broken down into 3 phases which can be used independently.

- Create a Project
- Create Project team members
- Create Operation Set
- Create Project tasks and Resource assignments
- Update Project Tasks
- Execute Operation Sets

The following is a complete list of the steps documented in the sample flow:

1. [Create PowerApps trigger](#1)
2. [Create Project](#2)
3. [Init Team Member](#3)
4. [Create Team Member](#4)
5. [Create Operation Set](#5)
6. [Create Project Buckets](#6)
7. [Init Linkstatus](#7)
8. [Init Number of tasks](#8)
9. [Init ProjectTaskID](#9)
10. [Do Until](#10)
11. [Set Project Task](#11)
12. [Create Project Task](#12)
13. [Create Resource Assignment](#13)
14. [Decrement Variable](#14)
15. [Rename Task](#15)
16. [Execute Operation Set](#16)

## Assumptions

This topic assumes that you have a basic knowledge of the Microsoft Dataverse platform, Cloud Flows, and the Schedule API. For more information, see the **References** section later in the topic.

## Flow Creation

### Select an environment

You can author the power automate flow on your environment.

1. Go to https://flow.microsoft.com and log in with your administrator credentials.
2. In the upper right corner, select **Environments**.
3. From the list, select the environment that has Dynamics 365 Project Operations installed.

### Create a solution

Complete the following steps to create a [solution aware flow](/power-automate/overview-solution-flows). The solution aware flow makes it easier to export the flow to use in the future.

1. In the navigation pane, select **Solutions**.
2. On the **Solutions** page, select **New Solution.**
3. On the **New solution** pane, fill in the required fields, and then select **Create**.


## <a id="1"></a>Step 1: Create PowerApps trigger

1. On the **Solutions** page, select the solution you created.
2. Select **New**.
3. In the left pane, select **Cloud flows** > **Automation** > **Cloud flow** > **Instant**.
4. In the **Flow name** field, enter **Schedule API Flow Demo.**
5. In the **Choose how to trigger this flow** list, select **Power Apps.** When you create a Power Apps trigger, the logic is up to you as the author. In this topic, leave the input parameters empty for testing purposes.
6. Select **Create.**

    ![./media/powerautomatetrigger.png](./media/powerautomatetrigger.png)


## <a id="2"></a>Step 2: Create a project 

Complete the following steps to create a sample project.

1. In the flow, select **+New Step**

    ![New Flow Step](media/newstep.png)

2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.

    ![Choose an Operation](media/chooseactiontab.png)

3. In the step, click on the **Ellipsis** and then select **Rename.**
4. Rename the step to **Create Project.**

   ![rename a step](media/renamestep.png)

5. In the **Action Name** field, select **msdyn_CreateProjectV1**.
6. In the **msdyn_subject** field, select **Add Dynamics Content**.
7. On the **Expression** tab, in the function box, enter **Project name – utcNow()**.
8. Select **OK.**

    ![expression builder](media/expressionbuilder.png)

## <a id="3"></a>Step 3: Init team member variable

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **initialize variable** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**
4. Rename the step to **Init team member**.
5. In the Name field, enter **TeamMemberAction**.
6. In the Type field, select **String**.
7. In the Value field, enter **msdyn_CreateTeamMemberV1**.   
  
## <a id="4"></a>Step 4: Create generic team member

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the new step, click on the ellipsis, and then select **Rename**
4. Rename the step to **Create Team Member**.
5. In the **Action Name** field, select **TeamMemberAction** from the **Dynamic Content** dialog.
6. In the **Action Parameters** field, enter:

   ```
   {
           "TeamMember": {
               "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projectteam",
               "msdyn_projectteamid": "@{guid()}",
               "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
               "msdyn_name": "ScheduleAPIDemoTM1"
                          }
    } 
    ```
     
Below is an explanation of each parameter:

- **@@odata.type**: entity name  ("Microsoft.Dynamics.CRM.msdyn_projectteam")
- **msdyn_name**: name of the team member. (“ScheduleAPIDemoTM1”)
- **msdyn_projectteamid**: is the primary key of the project team ID which is just a GUID expression
   
   ![inserting a guid](media/guid.png)
   
- **msdyn_project@odata.bind:** the project id of the owning project. This will be dynamic content coming from the response of the create project step. Ensure that you type the full path and add dynamic content between the brackets. Note that the quotes are necessary as well. E.g. **"/msdyn_projects(ADD DYNAMIC CONTENT)"**
 
## <a id="5"></a>Step 5: Create an operation set

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**. 
4. Rename the step to **Create Operation Set**.
5. In the Action Name field, select the Dataverse custom action **msdyn_CreateOperationSetV1**
6. In the Description field, enter **ScheduleAPIDemoOperationSet**
7. In the Project field, select enter **/msdyn_projects(**
8. Select **msdyn_CreateProjectV1Response ProjectId** from the Dynamic Content dialog.
9. In the Project field, enter **)**


## <a id="6"></a>Step 6: Create a project bucket

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, in the search box, enter **add a new row** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**. 
4. Rename the step to **Create Bucket**.
5. In the Table Name field, select **Project Buckets**
6. In the Name field, enter **ScheduleAPIDemoBucket1**
7. In the Project, select **msdyn_CreateProjectV1Response ProjectId** from the Dynamic Content dialog.


## <a id="7"></a>Step 7: Init Link Status

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **initialize variable** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**
4. Rename the step to **Init linkstatus**.
5. In the Name field, enter **linkstatus**.
6. In the Type field, select **Integer**.
7. In the Value field, enter **192350000**.   

## <a id="8"></a>Step 8: Init Number of tasks

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **initialize variable** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**
4. Rename the step to **Init Number of tasks**.
5. In the Name field, enter **number of tasks**.
6. In the Type field, select **Integer**.
7. In the Value field, enter **5**. 

## <a id="9"></a>Step 9: Init ProjectTaskID

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **initialize variable** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**
4. Rename the step to **Init ProjectTaskID**.
5. In the Name field, enter **number of tasks**.
6. In the Type field, select **String**.
7. In the Value field, enter **guid()**, in the Expression Builder. 

## <a id="10"></a>Step 10: Do Until

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **Do Unit** and select it from the results on the **Actions** tab.
3. Set the first value in the conditional statement to the **number of tasks** varible from the Dynamic Content
4. Set the condition to **less than equal to**.
5. Set the second value in the conditional statement to **0**

## <a id="11"></a>Step 11: Set Project Task

1. In the flow, select **+New Step**
2. In the **Choose an operation** dialog box, search for **set variable** and select it from the results on the **Actions** tab.
3. In the new step, click on the Ellipsis, and then select **Rename**
4. Rename the step to **Set Project Task**.
5. In the Name field, select **msdyn_projecttaskid**.
6. In the Value field, enter **guid()**, in the Expression Builder. 

## <a id="12"></a>Step 12: Create Project Task> 

In this step, we will create a Project Task that has a specific unique ID; belonging to the current Project and the previously created Project Bucket.

1. In the flow, select **+New Step**.
2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the step, click on the **Ellipsis** and then select **Rename.**
4. Rename the step to **Create Project Task.**
5. In the action name, select **msdyn_PssCreateV1**
6. In the entity field, enter:

   ```
   {
     "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projecttask",
     "msdyn_projecttaskid": "@{variables('msdyn_projecttaskid')}",
     "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
     "msdyn_subject": "ScheduleAPIDemoTask1",
     "msdyn_projectbucket@odata.bind": "/msdyn_projectbuckets(@{outputs('Create_Project_Buckets')?['body/msdyn_projectbucketid']})",
     "msdyn_start": "@{addDays(utcNow(), 1)}",
     "msdyn_scheduledstart": "@{utcNow()}",
     "msdyn_scheduledend": "@{addDays(utcNow(), 5)}",
     "msdyn_LinkStatus": "192350000"
   }
   ```
 
7. In the OperationSetId field, select **msdyn_CreateOperationSetV1Response** from the Dynamic Content dialog.


Below is the explanation of each parameter:

- **\@\@odata.type**: "Microsoft.Dynamics.CRM.msdyn_projecttask"
- **msdyn_projecttaskid**: Unique ID for the task. It should be set to dynamic variable from **msdyn_projecttaskid**
- **msdyn_project\@odata.bind**: The project id of the owning project. This will be a dynamics content coming from the response of the create project step. Ensure that you type the full path and add dynamic content between the brackets. Note that the quotes are necessary as well. E.g. "/msdyn_projects(ADD DYNAMIC CONTENT)"
- **msdyn_subject**: Any random task name
- **msdyn_projectbucket\@odata.bind**: Project bucket containing the tasks. This will be a dynamics content coming from the response of the create project bucket step. Ensure that you type the full path and add dynamic content between the brackets. Note that the quotes are necessary as well. E.g. "/msdyn_projectbuckets(ADD DYNAMIC CONTENT)"
- **msdyn_start**: dynamics content for the start date. E.g. Tomorrow would represented as “addDays(utcNow(), 1)”
- **msdyn_scheduledstart**: schedule start date. Same as above
- **msdyn_scheduleend**: schedule end date; select a data in the future. E.g. “addDays(utcNow(), 5)”
- **msdyn_LinkStatus**: "192350000"

## <a id="13"></a>Step 13: Create Assignment
============================
1. In the flow, select **+New Step**.
2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the step, click on the **Ellipsis** and then select **Rename.**
4. Rename the step to **Create Assignment.**
5. In the action name, select **msdyn_PssCreateV1**
6. In the entity field, enter:

   ```
   {
     "@odata.type": "Microsoft.Dynamics.CRM.msdyn_resourceassignment",
     "msdyn_resourceassignmentid": "@{guid()}",
     "msdyn_name": "ScheduleAPIDemoAssign1",
     "msdyn_taskid@odata.bind": "/msdyn_projecttasks(@{variables('msdyn_projecttaskid')})",
     "msdyn_projectteamid@odata.bind": "/msdyn_projectteams(@{outputs('Create_Team_Member')?['body/TeamMemberId']})",
     "msdyn_projectid@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})"
   }
   ```

7. In the OperationSetId field, select **msdyn_CreateOperationSetV1Response** from the Dynamic Content dialog.

## <a id="14"></a>Step 14: Decrement Variable

1. In the flow, select **+New Step**.
2. In the **Choose an operation** dialog box, in the search box, enter **decrement variable** and select it from the results on the **Actions** tab.
3. In the Name fied, select **number of tasks**
4. In the Value field, enter **1**.

## <a id="15"></a>Step 15: Rename Project Task

1. In the flow, select **+New Step**.
2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the action step, click on the **Ellipsis** menu and select **Rename**, to rename the step to **Rename Project Task**
4. In the Action Name field, select **msdyn_PssUpdateV1**.
5. In the Entity field, enter:

   ```
   {
              "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projecttask",
              "msdyn_projecttaskid": "@{variables('msdyn_projecttaskid')}",
              "msdyn_subject": "ScheduleDemoTask1-UpdatedName"
   }
   ```

6. In the OperationSetId field, select **msdyn_CreateOperationSetV1Response** from the Dynamic Content dialog.

## <a id="16"></a>Step 16: Execute Operation Set

1. In the flow, select **+New Step**.
2. In the **Choose an operation** dialog box, in the search box, enter **Perform an unbound action** and select it from the results on the **Actions** tab.
3. In the action step, click on the **Ellipsis** menu and select **Rename**, to rename the step to **Execute Operation Set**
4. In the Action Name field, select **msdyn_ExecuteOperationSetV1**
5. In the OperationSetId field, select **msdyn_CreateOperationSetV1Response OperationSetId** from the Dynamid Content dialog.
    

## References

- [Overview of how to integrate flows with Dataverse - Power Automate](/power-automate/dataverse/overview?WT.mc_id=email)
- [Use Project schedule APIs to perform operations with Scheduling entities](schedule-api-preview.md)
- [Overview of the cloud flows - Power Automate](/power-automate/overview-cloud?WT.mc_id=email)
- [Overview of solution-aware flows - Power Automate](/power-automate/overview-solution-flows?WT.mc_id=email)



