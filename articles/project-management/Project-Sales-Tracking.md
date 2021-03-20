---
# required metadata

title: Project sales tracking 
description: This topic provides information about how Project Operations tracks progress against labor revenue on the Project.
author: rumant
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: rumant
---

# Labor revenue tracking on Projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project Operations tracks labor estimates and revenue at the lowest required granularity on the Project Plan. The estimate of labor revenue is based on the planned effort and resources, generic or named assigned to each leaf-node task in the Project plan. As the project gets underway and people report time on various tasks of the project, the actual revenue on labor is summarized and then it triggers a calculation of the projections

## Labor Revenue Tracking view

The **Tracking** tab on the project has a dropdown called **Tracking**. Use this dropdown to select "Cost". This will open the **Cost tracking view**. Then using the dropdown called **Use** pick “Bill Rate”. This will open the **Revenue Tracking** view and it shows the progress of labor revenue on each task in the project plan. It also compares the actual labor revenue spent on a task to the task's planned labor revenue. Dynamics 365 Project Operations uses the following formulas to calculate labor revenue metrics:

- **Planned Revenue**: Estimated sales values of all resource assignments on each leaf node task
- **Actual Revenue**: Sum of all unbilled sales actuals for time recorded on the task
- **Billable Revenue%**: Actual revenue  ÷ Revenue Estimate at complete 
- **Remaining Revenue**: Revenue Estimate at complete – Actual revenue  
- **Estimated Revenue at Complete**: Remaining revenue + Actual revenue
- **Revenue variance**: Planned revenue – Estimated Revenue at complete 


>**Note**
>1. It is important to note that Project Operations only shows labor revenues in the tracking tab. While Materials and Expenses can be estimated and tracked for consumption, these revenues are not included in the revenues shown on the Tracking tab of the project. Tracking tab is designed to work only for reprojecting labor revenues via re-projection of effort.  
>2. All revenue amounts shown are converted to cost currency of the project. Cost currency of the project is the currency of the contracting unit on the project. 
>3. For Fixed Price Projects, i.e Projects mapped to a Fixed Price Contract line, revenue numbers on the Labor revenue tracking view are not relevant as unbilled sales actuals are not recorded on approval of time
>4. It is likely that the Estimated sales values for Time shown on the **Estimate tab** of the Project may not add up to the **Planned Revenue** value on the **Tracking** tab. The source of this discrepancy is due to 2 possible reasons:
><ol>
><li>Firstly **Estimates tab** shows Estimated Revenue in Sales currency while Tracking tab shows Planned Revenue converted to cost currency. </li>
><li>Secondly, when converting estimated sales in Contract currency as shown on the **Estimates** tab to Project currency, the conversion could involve 2 steps that that could result in some loss of precision: </li>
><ol>
><li>Estimated sales amount in contract currency is first converted to base currency (Conversion #1) and </li>
><li>Estimated sales amount in base currency is then converted to project cost currency (Conversion #2). </li>
></ol>
></ol>
><p>Currency Precision is applied in both steps to result in a **Planned Revenue** in project currency (Tracking tab) that deviates slightly from the **Planned Sales** in Contract currency values (Time - phased view on the **Estimates** tab).</p> 
   

## Reprojecting revenues on leaf node tasks

It is not possible to directly reproject labor revenues on a Project task on the tracking tab. However using the Effort Tracking view, a project manager can reproject the remaining effort on a task. This in turn will cause a recalculation of the remaining revenue on the task. Below is a description of this works:

1. A project manager can reproject effort on tasks by updating the default **Remaining Effort** with a new estimate of the **Remaining effort** on the task. 
This will cause a recalculation of the task's Effort Estimate At Complete, progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.

2. Based on the new value for **Remaining effort** on the task, the system calculates **Remaining revenue** on the **Revenue tracking view**. For calculating **Remaining Revenue** based on **Remaining effort**, the system first calculates the average revenue of one hour of effort on the task as Planned revenue/Planned effort. The planned revenue is the sum of the revenue of all resource assignments on the task. Average revenue per hour is used to compute **Remaining revenue** for the newly projected **Remaining effort** on the task
3. Estimated Revenue at Complete and Revenue Consumption percentage on the leaf-node task are re-calculated.

4. Revenue at Complete of the Summary tasks all the way to the root node are recalculated.

## Reprojection of revenues on summary tasks

Labor revenue on summary tasks or container tasks can also be re-projected. It is not possible to directly re-project labor revenues on a Summary Project task on the tracking tab. Similar to leaf node tasks, this can be done using the Effort Tracking view, where a project manager can reproject the remaining effort on a Summary task. This in turn will cause a recalculation of the remaining revenue on the Summary task. Below is a description of this works:

1. A project manager can reproject effort on tasks by updating the default **Remaining Effort** with a new estimate of the **Remaining effort** on the task. 
This will cause a recalculation of the task's Estimate At Complete, progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated and produce a new projection of effort variance.

2. Based on the new value for **Remaining effort** on the task, the system calculates **Remaining revenue** on the **Revenue tracking view**. For calculating **Remaining Revenue** based on **Remaining effort**, the system first calculates the average revenue of one hour of effort on the task as Planned revenue/Planned effort. The planned revenue is the sum of the revenue of all resource assignments on the task. It then uses this average revenue per hour and computes revenue of the newly projected **Remaining effort** on the task
 
3. The Estimated Revenue at Complete and Revenue Consumption percentage on the Summary task are re-calculated.

4. The new Estimated Revenue at Complete is distributed down to the child tasks in the same proportion as the original Planned Revenue was on the task.

5. The new Estimated Revenue at Complete on each of the individual tasks down to the leaf node tasks is calculated. Based on this value, the affected child tasks down to the leaf nodes will have their Remaining Revenue and Revenue Consumption percentage recalculated based on the Revenue at Complete value. This results in a new projection for the Revenue variance of the task. 

6. The Revenue at Complete of the Summary tasks all the way to the root node are recalculated.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

