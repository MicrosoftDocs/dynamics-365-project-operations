---
title: Project sales tracking 
description: This article provides information about how Project Operations tracks progress against labor revenue on a project.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project sales tracking

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations tracks labor estimates and revenue at the lowest required granularity on a project plan. The estimate of labor revenue is based on the planned effort and the generic or named resources that are assigned to each leaf node task in the project plan. When the project begins and people start to report time on various project tasks, the actual revenue on labor is summarized which starts a calculation of the projections.

## Labor revenue tracking view

On the **Projects** page, on the **Tracking** tab, you can select **Tracking** > **Cost** to open the **Cost Tracking** view. Or, you can select **Use** > **Bill Rate** to open the **Revenue Tracking** view, which shows the progress of labor revenue on each task in the project plan. This view also compares the actual labor revenue spent on a task to the task's planned labor revenue. Project Operations uses the following formulas to calculate labor revenue metrics:

- **Planned Revenue**: Estimated sales values of all resource assignments on each leaf node task
- **Actual Revenue**: Sum of all unbilled sales actuals for time recorded on the task
- **Billable Revenue%**: Actual revenue ÷ Revenue estimate at complete
- **Remaining Revenue**: Revenue estimate at complete – Actual revenue
- **Estimated Revenue at Complete**: Remaining revenue + Actual revenue
- **Revenue variance**: Planned revenue – Estimated revenue at complete


> [!NOTE]
> Project Operations only shows labor revenues on the **Project** page on the **Tracking** tab. While materials and expenses can be estimated and tracked for consumption, these revenues are not included in the revenues shown on the **Tracking** tab. This tab is designed to work only for reprojecting labor revenues by reprojecting effort.  
> All revenue amounts shown are converted to the cost currency of the project. The cost currency of the project is the currency of the contracting unit on the project. 
> For fixed price projects, revenue numbers on the **Labor revenue tracking** view aren't relevant because unbilled sales actuals aren't recorded on the approval of time.
> The estimated sales values for time that are shown on the **Estimate** tab of the project may not add up to the planned revenue value on the **Tracking** tab. The source of this discrepancy is due to two possible reasons:
><ol>
   ><li> The <b>Estimates</b> tab shows estimated revenue in the sales currency, while the <b>Tracking</b> tab shows planned revenue converted to the cost currency. </li>
   ><li> When estimated sales are converted to the contract currency as shown on the <b>Estimates</b> tab, to the project currency, the conversion involves steps that could result in some loss of accuracy: </li>
><ol>
><li> The estimated sales amount in the contract currency is first converted to the base currency (conversion 1).</li>
><li> The estimated sales amount in the base currency are converted to the project cost currency (conversion 2). </li>
></ol>
></ol>
> Currency precision is applied in both steps, which results in a deviation of the planned revenue in the project currency from the planned sales in the contract currency.
   

## Reprojecting revenues on leaf node tasks

Labor revenues on a leaf node task can't be directly reprojected on the **Tracking** tab on the **Project** page. However, you can use the **Effort Tracking** view to reproject the remaining effort on a task. This causes a recalculation of the remaining revenue on the task. The following is a description of how this works.

1. A project manager can reproject effort on tasks by updating the default value in the **Remaining Effort** field with a new estimate of the remaining effort on the task. 
Reprojecting causes a recalculation of the task's effort estimate at complete (EAC), progress percentage, and the projected effort variance on a task. The EAC, estimate to complete (ETC), and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.
2. Based on the new value for the remaining effort on the task, the system calculates the remaining revenue on the **Revenue Tracking** view. To calculate the remaining revenue based on the remaining effort, the system first calculates the average revenue of one hour of effort on the task as planned revenue or planned effort. The planned revenue is the sum of the revenue of all resource assignments on the task. The average revenue per hour is used to compute the remaining revenue for the newly projected remaining effort on the task.
3. The estimated revenue at complete and revenue consumption percentage on the leaf node task are re-calculated.
4. The revenue at complete value of the summary tasks all the way to the root node are recalculated.

## Reprojecting revenues on summary tasks

You can reproject labor revenue on summary tasks or container tasks. However, you can't directly reproject labor revenues on a summary project task on the **Tracking** tab on the **Project** page. Similar to leaf node tasks, reprojecting summary and container tasks can be done using the **Effort Tracking** view. In this view, you can reproject the remaining effort on a summary task causing a recalculation of the remaining revenue on the summary task. The following is a description of how this works.

1. A project manager can reproject effort on tasks by updating the default value in the **Remaining Effort** field with a new estimate of the **Remaining Effort** on the task. 
Reprojecting causes a recalculation of the task's estimate at complete (EAC), progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.
2. Based on the new value in the **Remaining effort** field on the task, the system calculates the remaining revenue in the **Revenue Tracking** view. To calculate the remaining revenue based on remaining effort, the system first calculates the average revenue of one hour of effort on the task as planned revenue or planned effort. The planned revenue is the sum of the revenue of all resource assignments on the task. This average revenue per hour  is then used to calculate the revenue of the newly projected remaining effort on the task.
3. The estimated revenue at complete and revenue consumption percentages on the summary task are re-calculated.
4. The new value for the estimated revenue at complete is distributed down to the child tasks in the same proportion as the original planned revenue was on the task.
5. The new estimated revenue at complete on each of the individual tasks down to the leaf node tasks is calculated. Based on this value, the affected child tasks down to the leaf nodes will have their remaining revenue and revenue consumption percentage recalculated based on the revenue at complete value. This results in a new projection for the revenue variance of the task. 
6. The revenue at complete value of the summary tasks all the way to the root node are recalculated.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

