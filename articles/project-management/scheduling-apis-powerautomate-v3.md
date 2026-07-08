---
title: Use V3 Project schedule APIs with Power Automate
description: Learn how to create a complete project plan using Power Automate and V3 Project schedule APIs. Follow step-by-step instructions to streamline your workflows.
author: dishantpopli
ms.date: 07/06/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Use V3 Project schedule APIs with Power Automate

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article describes a sample flow that shows how to use schedule API V3 version to create a complete project plan by using Microsoft Power Automate, and how to create, update, and delete schedulable entities. The example shows how to create a project, project team members, project tasks, and resource assignments, update project record, and delete existing resource assignments. This article shows how to use V3 API to perform multiple operations in a single step.

## Schedule API V3 Functioning and Capabilities

The V3 version of the Schedule API serves as a wrapper for the existing V2 APIs. Instead of requiring users to create an operation set, load data, and execute the operation set through separate APIs, V3 consolidates these steps into a single API call to reduce multiple network requests. This version supports create, update, and delete operations within one request. Internally, the API creates an operation set, stages the specified changes, and executes the operation set. Delete operations are processed first, followed by create operations, and finally update operations.

## Assumptions

This article assumes that you have a basic knowledge of the Microsoft Dataverse platform, cloud flows, and the Project Schedule API. 

Here's a complete list of the steps to create the sample flow in this article:

1. [Create a PowerApps trigger](#1)
1. [Create a project](#2)
1. [Retrieve default bucket](#3)
1. [Create generic team members](#4)
1. [Initialize required variables](#5)
1. [Prepare task and assignment payload](#6)
1. [Create tasks and assignments using Schedule API V3](#7)
1. [Add delay for operation set to complete](#8)
1. [Initialize variables for the next operation](#9)
1. [Delete assignments](#10)
1. [Create new assignments](#11)
1. [Update tasks](#12)
1. [Reassign tasks from team member A to team member B and update task names using Schedule API V3](#13)

## Create a flow

### Select an environment

To create the Power Automate flow in your environment, follow these steps:

1. Go to <https://flow.microsoft.com>, and use your administrator credentials to sign in.
1. In the upper-right corner, select **Environments**.
1. In the list, select the environment where Dynamics 365 Project Operations is installed.

### Create a solution

Follow these steps to create a [solution-aware flow](/power-automate/overview-solution-flows). By creating a solution-aware flow, you can more easily export the flow to use it later.

To create a solution, follow these steps:

1. On the navigation pane, select **Solutions**.
1. On the **Solutions** page, select **New solution**.
1. In the **New solution** dialog box, set the required fields, and then select **Create**.

## <a id="1"></a>Step 1: Create a PowerApps trigger

To create a PowerApps trigger, follow these steps:

1. On the **Solutions** page, select the solution that you created, and then select **New**.
1. In the left pane, select **Cloud flows** \> **Automation** \> **Cloud flow** \> **Instant**.
1. In the **Flow name** field, enter **Schedule API Demo Flow**.
1. In the **Choose how to trigger this flow** list, select **Power Apps**. When you create a Power Apps trigger, you define the logic. For the example in this article, leave the input parameters blank for testing purposes.
1. Select **Create**.

## <a id="2"></a>Step 2: Create a project

To create a sample project, follow these steps:

1. In the flow that you created, select **New step**.
1. In the **Choose an operation** dialog box, enter **perform unbound action** in the search field. On the **Actions** tab, select the operation in the list of results.

    :::image type="content" source="media/chooseactiontab.png" alt-text="Screenshot of selecting an operation.":::

1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Create Project**.
1. In the **Action Name** field, select **msdyn\_CreateProjectV1**.
1. Under the **msdyn\_subject** field, select **Add dynamic content**.
1. On the **Expression** tab, in the function field, enter **concat('Project name - ',utcNow())**.
1. Select **OK**.

## <a id="3"></a>Step 3: Retrieve default bucket

To retrieve the default bucket, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **List rows**. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Retrieve Default Bucket**.
1. In the **Table name** field, select **Project Buckets**.
1. In the **Filter rows** field, enter **_msdyn_project_value eq @{outputs('Create_Project')?['body/ProjectId']}**.
1. In the **Row count** field, enter **1**.

     :::image type="content" source="media/get-default-bucket.png" alt-text="Screenshot of get default bucket.":::

## <a id="4"></a>Step 4: Create generic team members

To create generic team members, follow the steps in each of the following sections:

1. Step 4.1: Init Team Member Create Action Name
1. Step 4.2: Create a generic team member A
1. Step 4.3: Create a generic team member B

### Step 4.1: Init Team Member Create Action Name

To initialize the team member create action name, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Initialize variable**. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Team Member Create Action Name**.
1. In the **Name** field, enter **TeamMemberAction**.
1. In the **Type** field, select **String**.
1. In the **Value** field, enter **msdyn_CreateTeamMemberV1**.

### Step 4.2: Create a generic team member A

To create a generic team member A, follow these steps:

1. In the flow, select **New step**.
1. In **Choose an operation**, enter **perform unbound action** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Create Team Member A**.
1. For the **Action Name** field, select **TeamMemberAction** in the **Dynamic content** dialog box.
1. In the **Action Parameters** field, enter the following parameter information.

```json
{
  "TeamMember": {
    "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projectteam",
    "msdyn_projectteamid": "@{guid()}",
    "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
    "msdyn_name": "ScheduleAPIDemoTM1"
  }
}
```

   :::image type="content" source="media/create-generic-team-member-a.png" alt-text="Screenshot of create a generic team member A.":::

### Step 4.3: Create a generic team member B

To create a generic team member B, follow these steps:

1. In the flow, select **New step**.
1. In **Choose an operation**, enter **perform unbound action** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Create Team Member B**.
1. For the **Action Name** field, select **TeamMemberAction** in the **Dynamic content** dialog box.
1. In the **Action Parameters** field, enter the following parameter information.

```json
{
  "TeamMember": {
    "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projectteam",
    "msdyn_projectteamid": "@{guid()}",
    "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
    "msdyn_name": "ScheduleAPIDemoTM2"
  }
}
```

   :::image type="content" source="media/create-generic-team-member-b.png" alt-text="Screenshot of create a generic team member B.":::

## <a id="5"></a>Step 5: Initialize required variables

To initialize required fields, follow the steps in each of the following sections:

1. Step 5.1: Initialize the task ID
1. Step 5.2: Initialize the assignment ID
1. Step 5.3: Initialize the payload array
1. Step 5.4: Initialize the task IDs
1. Step 5.5: Initialize the assignment IDs
1. Step 5.6: Initialize the number of tasks

### Step 5.1: Initialize the task ID

To initialize the task ID, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Task Id**.
1. In the **Name** field, enter **task id**.
1. In the **Type** field, select **String**.
1. For the **Value** field, enter **guid()** in the expression builder.

### Step 5.2: Initialize the assignment ID

To initialize the assignment ID, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Assignment Id**.
1. In the **Name** field, enter **assignment id**.
1. In the **Type** field, select **String**.
1. For the **Value** field, enter **guid()** in the expression builder.

### Step 5.3: Initialize the payload array

To initialize the payload array, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Payload Array**.
1. In the **Name** field, enter **tasks and assignments**.
1. In the **Type** field, select **Array**.
1. For the **Value** field, enter **empty** in the expression builder.

### Step 5.4: Initialize the task IDs

To initialize the task IDs, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Task Ids**.
1. In the **Name** field, enter **task ids**.
1. In the **Type** field, select **Array**.
1. For the **Value** field, enter **empty** in the expression builder.

### Step 5.5: Initialize the assignment IDs

To initialize the assignment IDs, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Assignment Ids**.
1. In the **Name** field, enter **assignment ids**.
1. In the **Type** field, select **Array**.
1. For the **Value** field, enter **empty** in the expression builder.

### Step 5.6: Initialize the number of tasks

To initialize the number of tasks, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Number of Tasks**.
1. In the **Name** field, enter **number of tasks**.
1. In the **Type** field, select **Integer**.
1. For the **Value** field, enter **5** in the expression builder.

## <a id="6"></a>Step 6: Prepare the task and assignment payload

To prepare the task and assignment payload, follow the steps in each of the following sections:

1. Step 6.1: Add the do until loop
1. Step 6.2: Set the task ID
1. Step 6.3: Add a task ID to the list
1. Step 6.4: Set the assignment ID
1. Step 6.5: Add an assignment ID to the list
1. Step 6.6: Add a task to the payload array
1. Step 6.7: Add assignments to the payload array
1. Step 6.8: Create a decrement variable

### Step 6.1: Add the do until loop

To add the do until loop, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **do until**. Then, on the **Actions tab**, select the operation in the list of results.
1. Set the **first value** in the conditional statement to the **number of tasks** variable from the Dynamic content dialog box.
1. Set the **condition** to less than or equal to*.
1. Set the **second value** in the conditional statement to **0**.

   :::image type="content" source="media/do-until.png" alt-text="Screenshot of do until.":::

### Step 6.2: Set the task ID

To set the task ID, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **set variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Set Task ID**.
1. In the **Name** field, select **task id**.
1. For the **Value** field, enter **guid()** in the expression builder.

### Step 6.3: Add a task ID to the list

To add a task ID to the list, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Task ID to List**.
1. In the **Name** field, select **task ids**.
1. For the **Value** field, enter **task id** from the Dynamic content dialog box.

### Step 6.4: Set the assignment ID

To set the assignment ID, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **set variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Set Assignment ID**.
1. In the **Name** field, select **assignment id**.
1. For the **Value** field, enter **guid()** in the expression builder.

### Step 6.5: Add an assignment ID to the list

To add an assignment ID to the list, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Assignment ID to List**.
1. In the **Name** field, select **assignment ids**.
1. For the **Value** field, enter **assignment id** from the Dynamic content dialog box.

### Step 6.6: Add a task to the payload array

To add a task to the payload array, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Task to Payload Array**.
1. In the **Name** field, select **tasks and assignments**.
1. For the **Value** field, enter.

```json
{
  "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projecttask",
  "msdyn_projecttaskid": "@{variables('task id')}",
  "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
  "msdyn_subject": "ScheduleAPIDemoTask1",
  "msdyn_projectbucket@odata.bind": "/msdyn_projectbuckets(@{outputs('Retrieve_Default_Bucket')?['body/value'][0]['msdyn_projectbucketid']})",
  "msdyn_start": "@{addDays(utcNow(), 1)}",
  "msdyn_scheduledstart": "@{utcNow()}",
  "msdyn_scheduledend": "@{addDays(utcNow(), 5)}",
  "msdyn_LinkStatus": "192350000"
}
```

   :::image type="content" source="media/add-task-to-payload-array.png" alt-text="Screenshot of add task to payload array.":::

### Step 6.7: Add assignments to the payload array

To add assignments to the payload array, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Assignment to Payload Array**.
1. In the **Name** field, select **tasks and assignments**.
1. For the **Value** field, enter.

```json
{
  "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_resourceassignment",
  "msdyn_resourceassignmentid": "@{variables('assignment id')}",
  "msdyn_name": "ScheduleAPIDemoAssign",
  "msdyn_taskid@odata.bind": "/msdyn_projecttasks(@{variables('task id')})",
  "msdyn_projectteamid@odata.bind": "/msdyn_projectteams(@{outputs('Create_Team_Member_1')?['body/TeamMemberId']})",
  "msdyn_projectid@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})"
}
```

   :::image type="content" source="media/add-assignments-to-payload-array.png" alt-text="Screenshot of add assignments to payload array.":::

### Step 6.8: Create a decrement variable

To create a decrement variable, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **decrement variable**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Decrement Variable**.
1. In the **Name** field, select **number of tasks**.
1. For the **Value** field, enter **1**.

## <a id="7"></a>Step 7: Create tasks and assignments with schedule API V3

To create tasks and assignments with schedule API V3, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Perform unbound action**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Create Tasks and Assignments**.
1. For the **Action Name** field, select **msdyn_ExecuteOperationSetV3**.
1. In the **ProjectId** field, enter **@outputs('Create_Project')?['body/ProjectId']** from Expression dialog box.
1. In the **OperationSetDescription** field, enter **ScheduleAPIDemoOperationSet**.
1. In the **CreateEntityCollection** field, select **Switch Input to Entire Array**.
1. For the **CreateEntityCollection** field, select **tasks and assignments** in the Dynamic content dialog box.

   :::image type="content" source="media/create-tasks-assignments.png" alt-text="Screenshot of create tasks and assignments.":::

## <a id="8"></a>Step 8: Add delay for operation set to complete

To add delay for operation set to complete, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Delay**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Delay For Operation Set to Complete**.
1. In the **Count** field, enter **20**.
1. In the **Unit** field, select **Second**.

## <a id="9"></a>Step 9: Initialize the variables for the next operation

To initialize the variables for the next operation, follow the steps in each of the following sections:

1. Step 9.1: Initialize create records
1. Step 9.2: Initialize update records
1. Step 9.3: Initialize delete records

### Step 9.1: Initialize create records

To initialize create records, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Create Records**.
1. In the **Name** field, enter **create records**.
1. In the **Type** field, select **Array**.
1. Keep the **Value** field empty.

### Step 9.2: Initialize update records

To initialize update records, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Update Records**.
1. In the **Name** field, enter **update records**.
1. In the **Type** field, select **Array**.
1. Keep the **Value** field empty.

### Step 9.3: Initialize delete records

To initialize delete records, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, enter **Initialize variable** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Init Delete Records**.
1. In the **Name** field, enter **delete records**.
1. In the **Type** field, select **Array**.
1. Keep the **Value** field empty.

## <a id="10"></a>Step 10: Delete assignments

To delete assignments, follow the steps in each of the following sections:

1. Step 10.1: Prepare the assignments to delete
1. Step 10.2: Add the assignments to delete

### Step 10.1: Prepare the assignments to delete

To prepare the assignments to delete, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Apply to each**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Prepare assignments to delete**.
1. In the “**Select an output from previous steps**” field, select **assignment ids** from the Dynamic content dialog box.

### Step 10.2: Add the assignments to delete

To add the assignments to delete, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Assignments to Delete**.
1. In the **Name** field, select **delete records**.
1. For the **Value** field, enter.

```json
{
  "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_resourceassignment",
  "msdyn_resourceassignmentid": "@{items('Prepare_Assignments_to_Delete')}",
  "msdyn_projectid@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})"
}
```

   :::image type="content" source="media/add-assignments-to-delete.png" alt-text="Screenshot of add assignments to delete.":::

## <a id="11"></a>Step 11: Create new assignments

To create new assignments, follow the steps in each of the following sections:

1. Step 11.1: Prepare the new assignments to create
1. Step 11.2: Add the new assignments to create

### Step 11.1: Prepare the new assignments to create

To prepare the new assignments to create, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Apply to each**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Prepare New Assignments to Create**.
1. In the “**Select an output from previous steps**” field, select **task ids** from the Dynamic content dialog box.

### Step 11.2: Add the new assignments to create

To add the new assignments to create, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add New Assignments to Create**.
1. In the **Name** field, select **create records**.
1. For the **Value** field, enter.

```json
{
  "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_resourceassignment",
  "msdyn_resourceassignmentid": "@{guid()}",
  "msdyn_name": "ScheduleAPIDemoAssign",
  "msdyn_taskid@odata.bind": "/msdyn_projecttasks(@{items('Prepare_New_Assignments_to_Create')})",
  "msdyn_projectteamid@odata.bind": "/msdyn_projectteams(@{outputs('Create_Team_Member_2')?['body/TeamMemberId']})",
  "msdyn_projectid@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})"
}
```

   :::image type="content" source="media/add-new-assignments-to-create.png" alt-text="Screenshot of add new assignments to create.":::

## <a id="12"></a>Step 12: Update the tasks

To update the tasks, follow the steps in each of the following sections:

1. Step 12.1: Prepare the tasks to update
1. Step 12.2: Add the tasks to update

### Step 12.1: Prepare the tasks to update

To prepare the tasks to update, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Apply to each**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Prepare Tasks to Update**.
1. In the “**Select an output from previous steps**” field, select **task ids** from the Dynamic content dialog box.

### Step 12.2: Add the tasks to update

To add the tasks to update, follow these steps:

1. In the flow, select **New step**.
1. In the **Choose an operation** dialog box, in the search field, enter **Append to array**. Then, on the **Actions tab**, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Add Tasks to Update**.
1. In the **Name** field, select **update records**.
1. For the **Value** field, enter.

```json
{
  "@@odata.type": "Microsoft.Dynamics.CRM.msdyn_projecttask",
  "msdyn_projecttaskid": "@{items('Prepare_Tasks_to_Update')}",
  "msdyn_project@odata.bind": "/msdyn_projects(@{outputs('Create_Project')?['body/ProjectId']})",
  "msdyn_subject": "Schedule API Demo Task Update"
}
```

   :::image type="content" source="media/add-tasks-to-update.png" alt-text="Screenshot of add tasks to update.":::

## <a id="13"></a>Step 13: Reassign the tasks from team member A to team member B and update the task names by using Schedule API V3

To reassign the tasks from team member A to team member B and update the task names by using Schedule API V3, follow these steps:

1. In the flow, select **New step**.
1. In **Choose an operation**, enter **perform unbound action** in the search field. Then, on the **Actions** tab, select the operation in the list of results.
1. In the new step, select the ellipsis (**&hellip;**), and then select **Rename**.
1. Rename the step **Perform Create, Update and Delete Operation**.
1. For the **Action Name** field, select **msdyn_ExecuteOperationSetV3**.
1. In the **ProjectId** field, enter **@outputs('Create_Project')?['body/ProjectId']** from Expression dialog box.
1. In the **OperationSetDescription** field, enter **ScheduleAPIDemoOperationSetNew**.
1. In the **CreateEntityCollection** field, select **Switch Input to Entire Array**.
1. For the **CreateEntityCollection** field, select **create records** in the Dynamic content dialog box.
1. In the **UpdateEntityCollection** field, select **Switch Input to Entire Array**.
1. For the **UpdateEntityCollection** field, select **update records** in the Dynamic content dialog box.
1. In the **DeleteEntityCollection** field, select **Switch Input to Entire Array**.
1. For the **DeleteEntityCollection** field, select **delete records** in the Dynamic content dialog box.

   :::image type="content" source="media/perform-create-update-delete-operation.png" alt-text="Screenshot of perform create, update, and delete operation.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
