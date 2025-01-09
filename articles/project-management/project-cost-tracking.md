---
title: Project cost tracking 
description: This article provides information about how Project Operations tracks progress against labor cost and spend on a project.
author: abriccetti
ms.date: 01/09/2025
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Labor cost tracking on projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations tracks labor estimates and spend at the lowest required granularity on the project plan. The financial estimate of labor cost is based on the planned effort and the generic or named resources that are assigned to each leaf-node task in the project plan. When the project begins and people start to report time on various project tasks, the actual spend on labor is summarized which starts a calculation of the projections.

## Labor Cost Tracking view

On the **Projects** page, on the **Tracking** tab, you can select **Tracking** > **Cost** to open the **Cost Tracking** view and see the progress of labor spend on each task in the project plan. This view also compares the actual labor cost spent on a task to the task's planned labor cost. Project Operations uses the following formulas to calculate labor cost metrics:

- **Planned cost**: Estimated cost of all resource assignments on each leaf node task
- **Actual Cost**: Sum of all cost actuals for time recorded on the task
- **Cost consumption percentage**: Actual cost ÷ Cost estimate at complete
- **Remaining Cost**: Cost estimate at complete  – Actual cost
- **Cost at Complete**: Remaining cost + Actual cost
- **Cost variance**: Planned cost – Cost estimate at complete

Each task shows a projection of the cost variance on the task. If the cost estimate at complete is more than the planned cost, the task is projected to go over budget. If the cost estimate at complete is less than the planned cost, the task is projected to finish under budget.

>[!NOTE]
> Project Operations only shows labor costs on the **Project** page on the **Tracking** tab. While materials and expenses can be estimated and tracked for consumption, these costs are not included in the costs shown on the **Tracking** tab. This tab is designed to work only for reprojecting labor costs by reprojecting effort.
All cost amounts shown are converted to the project's cost currency from the project's cost price currency used to determine the cost rate. The cost currency of the project is the currency of the contracting unit on the project. The estimated cost values for time that are shown on the **Time phased estimates** tab on the **Project** page might not add up to the planned cost on the **Tracking** tab. The reason for this discrepancy is because of the differences in how estimated cost is summarized on the **Time phased estimates** grid and how planned cost is calculated on the **Tracking** grid. 
>
> - The **Time phased estimates tab** calculates the estimated cost by using the same currency of the cost rate in the price list. Then, the estimated cost in the price list currency is converted to the estimated cost in the project's cost currency. The estimated cost in the project currency is shown rounded to 2 decimal places. At no point during this conversion is currency precision applied. 
> - On the **Tracking** tab, the planned cost calculation follows a slightly different calculation order that involves currency precision being applied in two stages: 
   ><ol>
   ><li>The estimated cost amount in the price list currency is converted to the base currency (conversion 1).</li>
   ><li>The estimated cost amount in the base currency is converted to the project cost currency (conversion 2). </li>
   ></ol>
   >Currency precision is applied in both steps to get a planned cost (on the **Tracking** tab) that deviates slightly from the estimated cost (on the **Time - phased** view on the **Time phased estimates** tab). 
   
## Reprojecting costs on leaf node tasks

Labor costs on a leaf node task can't be directly reprojected on the **Tracking** tab on the **Project page**. However, you can use the **Effort Tracking** view to reproject the remaining effort on a task. This causes a recalculation of the remaining cost on the task. The following is a description of how this works.

1. A project manager can reproject effort on tasks by updating the default value in the **Remaining Effort** field with a new estimate of the remaining effort on the task. 
Reprojecting causes a recalculation of the task's effort estimate at complete (EAC), progress percentage, and the projected effort variance on a task. The EAC, estimate to complete (ETC), and progress percentages on the summary tasks are also recalculated and produce a new projection of effort variance.
2. Based on the new value for the remaining effort on the task, the system calculates the remaining cost on the **Cost Tracking** view. To calculate the remaining cost based on the remaining effort, the system first calculates the average cost of one hour of effort on the task as planned cost or planned effort. The planned cost is the sum of the cost of all resource assignments on the task. The average cost per hour is used to compute the remaining cost for the newly projected remaining effort on the task.
3. The cost at complete and cost consumption percentage on the leaf-node task are recalculated.
4. The cost at complete value of the summary tasks all the way to the root node are recalculated.

## Reprojecting costs on summary tasks

You can reproject labor costs on summary tasks or container tasks. However, you can't directly reproject labor cost on a summary project task on the **Tracking** tab on the **Project** page. Similar to leaf node tasks, reprojecting summary and container tasks can be done using the **Effort Tracking** view. In this view, you can reproject the remaining effort on a summary task causing a recalculation of the remaining cost on the summary task. The following list describes how this works.

1. A project manager can reproject effort on summary tasks by updating the default value of the remaining effort with a new estimate on the task. This update causes a recalculation of the summary task's estimate at complete (EAC), progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.
2. Based on the new value for remaining effort on the summary task, the system calculates the remaining cost on the **Cost Tracking** view. To calculate the remaining cost based on the remaining effort, the system first calculates the average cost of one hour of effort on the summary task as planned cost or planned effort. The average cost per hour is used to calculate the cost of the newly projected remaining effort on the summary task.
3. The cost at complete and cost consumption percentage on the summary task are recalculated.
4. The new cost at complete is distributed down to the child tasks in the same proportion as the original planned cost was on the task.
5. The new cost at complete value on each of the individual tasks down to the leaf node tasks is calculated. Based on this value, the affected child tasks down to the leaf nodes have their remaining cost and cost consumption percentage recalculated based on the cost at complete value. This value results in a new projection for the cost variance of the task. 


The **Cost performance** field can be set from the tracking data. When the cost variance for the root node in the **Cost tracking** view is negative, you can set this field to **Under Budget**. When the cost variance for the root node is positive, you can set the value to **Over Budget**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
