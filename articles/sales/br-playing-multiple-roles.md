---
title: Estimate project sales and costs when a bookable resource fills multiple roles on a project 
description: This article explains how to use pricing dimensions to support pricing and costing estimates for a resource that fills multiple roles on a project.
author:  abriccetti
ms.author: abriccetti
ms.date: 01/09/2025  
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

--- 

# Estimate project sales and costs when a bookable resource fills multiple roles on a project 

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core, Project Operations for manufacturing-based scenarios_ 

Project-based companies often have the need for one resource to fill multiple roles on a project. Each role can be priced and costed differently. This means that the same resource's time on a project could get a different financial estimate depending on the bill and cost rates for each role. You can set up the values on the team member record for the named resource with different overrides on each of the tasks that the team member is assigned to.

The following example walks you through how the simple override of a value allows a resource to have multiple roles on a project with different cost and bill rates.

## Create tasks
To create tasks, you need to add tasks, as well as summary tasks, after which you need to assign the task before you add task duration. 

### Add tasks and summary tasks
To add a task, complete the following steps.

1. Go to **Projects** and open the project to which you want to add tasks.
2. Select **Add new task**. Name the task, and then press **Enter**.
3. Enter another task name and press **Enter**. Repeat this until you have a full list of tasks.
3. To indent tasks under **Summary** tasks, select the three vertical dots by the task name, and then select **Make subtask**. 

  > [!TIP]
  > To select more than one task, select a task, press and hold **Ctrl**, and then select another task.
  >
  > You can also choose **Promote subtask** to move tasks out from under **Summary** tasks.

### Assign tasks

Complete the following steps to assign tasks.

1. In the  **Assigned to**  column for a task, select the person icon.
2. Choose a team member from the list or enter text to search for a name.

### Add task duration and columns

It's often easiest to begin constructing your project with duration. Complete the following steps to add a task duration.

1. In the **Duration** column for a task, type the number of days you think it will take to accomplish the task. If you want to use a different unit of time, enter a number plus the word **hours**, **weeks**, or **months**.
2. If you want your task to appear as a diamond-shaped milestone in the **Timeline** view, in the **Duration** column, enter **0 days** .
3. Press **Enter**  to go to the next task's **Duration** field and continue entering durations.

  > [!NOTE]
  > You can't enter a duration for summary tasks.

You can add columns to your project to provide more details. To do this, select **Add column**. 

For more information, see [Create a project](https://support.microsoft.com/en-us/office/create-a-project-a5b5e823-fb2e-45fd-be00-7d84422d9749).

## Set up the role and organization unit for a generic project team member
Complete the following steps to set up a role and organizational unit for a generic team member.

1. On the **Tasks** page, select the **Task** row for **Task A**. 
2. In **Assigned To**, select **Add generic resource**. This opens the **Team Member Quick Create** page.
3. On the **Team Member Quick Create** page, specify the attributes of the generic team member who can perform this task.
4. Select the appropriate role and organizational unit, and then select **Save and Close**. A generic team member is created and assigned to this task. 
5. Repeat steps 1-4 for **Task B**. However, **Task B** must have a different role and organizational unit assigned for the generic team member than **Task A**. 

## Set up the role and organization unit for a project task
Complete the following steps to set up a role and organizational unit for a task.

1. After you create **Task A**, select the task, and then select the **i** icon to open the **Task Details** pane. 
2. On the **Task Details** pane, scroll to the bottom and select **View Details** to open the **Task Details** page.
3. On the **Task Details** page, in **Role** and **Organizational Unit**, add the values that are required to perform this task for the resource. 

  > [!NOTE]
  > If you complete this scenario using the Project Operations demo data, select **Consulting Lead** for the role, and **Fabrikam US** as the organizational unit.

4. Select **Task B**, and then select the task.
5. Select the **i** icon to open **Task Details** pane. 
6. On the **Task Details** pane, scroll to the bottom and select **View details** to open the **Task Details** page.
7. On the **Task Details** page, in **Role** and **Organizational Unit**, add the values that are required of a resource that would perform this task. The values in **Role** and **Organizational Unit** for **Task B** must be different than those for **Task A**. 

  > [!NOTE]
  > If you complete this scenario using the Project Operations demo data, select **Network Technician** for the role, and **Fabrikam US** as the organizational unit.

8. Save and close the **Task Details** page. 

## Team member and estimates behavior 
To understand the behavior on the **Team Member** grid and the estimates, complete the following steps.

1. On the **Team Member** grid, select the two generic team members, and then select **Generate Requirements**. This will generate resource requirements. 
2. Select the team member row for **Consulting Lead**, and then select **Book**. The schedule board opens with a list of resources. Select a resource and then select **Book** to book the resource to that requirement.
3. Select the team member row for **Network Technician**, and then select **Book**. The schedule board opens with a list of resources. Select the same resource as above and then select **Book** to book the resource to that requirement.

### Team Member grid 

On the **Team Member** grid, the two generic team member records are deleted and replaced with only one resource. There is one set of values for that resource, which are a default set of values for **Role** and **Organizational Unit**.

When you expand the row for that team member record, you can see distinct assignments on the team member record for both tasks. Each assignment row has task-specific values for **Role** and **Organizational Unit**. 

### Estimates grid 

On the **Estimates** grid, both assignments for the same resource are priced differently. The assignment for the resource on **Task A** is priced using the **Role** attribute value of **Consulting Lead**. The assignment for the same resource on **Task B** is priced using the **Role** attribute value of **Network Technician**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
