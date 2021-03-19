---
# required metadata

title: Project cost tracking 
description: This topic provides information about how Project Operations tracks progress against labor cost and spend on the Project.
author: rumant
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: rumant
---

# Labor cost tracking on Projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project Operations tracks labor estimates and spend at the lowest required granularity on the Project Plan. The financial estimate of labor cost is based on the planned effort and resources, generic or named assigned to each leaf-node task in the Project plan. As the project gets underway and people report time on various tasks of the project, the actual spend on labor is summarized and then it triggers a calculation of the projections

## Labor Cost Tracking view

The **Tracking** tab on the project has a dropdown called **Tracking**. Use this dropdown to select "Cost". This will open the **Cost tracking view**  and it shows the progress of labor spend on each task in the project plan. It also compares the actual labor cost spent on a task to the task's planned labor cost. Dynamics 365 Project Operations uses the following formulas to calculate labor cost metrics:

- **Cost consumption percentage**: Actual cost  ÷ Cost Estimate at complete 
- **Remaining Cost**: Cost Estimate at complete  – Actual cost  
- **Cost at Complete**: Remaining cost + Actual cost
- **Cost variance**: Planned cost – Cost Estimate at complete 

Each task shows a projection of the cost variance on the task. If the Cost Estimate at complete  is more than planned cost, the task is projected to go over budget. If the Cost Estimate at complete is less than the planned cost, the task is projected to finish under budget.

>**Note**
>It is important to note that Project Operations only shows labor costs in the tracking tab. While Materials and Expenses can be estimated and tracked for consumption, these costs are not included in the costs on the Tracking tab of the project. Tracking tab is designed to work only for reprojecting labor costs via re-projection of effort.  

## Reprojecting costs on leaf node tasks

It is not possible to directly reproject labor costs on a Project task on the tracking tab. However using the Effort Tracking view, a project manager can reproject the remaining effort on a task. This in turn will cause a recalculation of the remaining cost on the task. Below is a description of this works:

1. A project manager can reproject effort on tasks by updating the default **Remaining Effort** with a new estimate of the **Remaining effort** on the task. 
This will cause a recalculation of the task's Estimate At Complete, progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.

2. Based on the new value for **Remaining effort** on the task, the system calculates **Remaining cost** on the **Cost tracking view**. For calculating **Remaining Cost** based on **Remaining effort**, the system first calculates the average cost of one hour of effort on the task as Planned cost/Planned effort. The planned cost is the sum of the cost of all resource assignments on the task. It then uses this average cost per hour and computes cost of the newly projected **Remaining effort** on the task

3.The Cost at Complete and Cost Consumption percentage on the leaf-node task are re-calculated.

4.The Cost at Complete of the Summary tasks all the way to the root node are recalculated.

## Reprojection of costs on summary tasks

Labor cost on summary tasks or container tasks can also be reprojected. It is not possible to directly reproject labor costs on a Summary Project task on the tracking tab. Similar to leaf node tasks, this can done using the Effort Tracking view, where a project manager can reproject the remaining effort on a Summary task. This in turn will cause a recalculation of the remaining cost on the Summary task. Below is a description of this works:

1. A project manager can reproject effort on tasks by updating the default **Remaining Effort** with a new estimate of the **Remaining effort** on the task. 
This will cause a recalculation of the task's Estimate At Complete, progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.

2. Based on the new value for **Remaining effort** on the task, the system calculates **Remaining cost** on the **Cost tracking view**. For calculating **Remaining Cost** based on **Remaining effort**, the system first calculates the average cost of one hour of effort on the task as Planned cost/Planned effort. The planned cost is the sum of the cost of all resource assignments on the task. It then uses this average cost per hour and computes cost of the newly projected **Remaining effort** on the task
 
3. The Cost at Complete and Cost Consumption percentage on the Summary task are re-calculated.

4. The new Cost at Complete is distributed down to the child tasks in the same proportion as the original Planned Cost was on the task.

5. The new Cost at Complete on each of the individual tasks down to the leaf node tasks is calculated. Based on this calue, the affected child tasks down to the leaf nodes will have their Remaining Cost and Cost Consumption percentage recalculated based on the Cost at Complete value. This results in a new projection for the Cost variance of the task. 

6. The Cost at Complete of the Summary tasks all the way to the root node are recalculated.


The **Cost performance** fields are set from the tracking date. When the cost variance for the root node in the **Cost tracking** view are negative, you can set these fields to **Under Budget**. When the cost variance for the root node are positive, you can set them to **Over Budget**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
