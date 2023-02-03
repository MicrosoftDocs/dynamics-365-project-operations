---
title: Financial estimates for resource time on projects
description: This article provides information about how financial estimates for time are calculated.
author: rumant
ms.date: 2/3/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Financial estimates for resource time on projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Financial estimates for time are calculated based on three factors: 

- The type of generic or named team member assigned to each leaf node task on the project plan. 
- The type or complexity of work.
- The spread of effort for the resource's assignment on the task. 

The first two factors influence the unit cost or bill rate of a resource's assignment. The unit cost or bill rate of a resource assignment is determined by the attributes of the resource assigned. These attributes include the organizational unit to which the resource belongs and the standard role of the resource. You can also add custom attributes relevant to your business for the resource, like standard title or experience level, and have them influence the unit cost or bill rate of the assignment.
In addition to the attributes of the resource, attributes of work, such as the task, can also influence the unit bill rate or cost rate of the assignment. For example, when certain tasks are more complex, the resource's assignment to those specific tasks result in a higher unit cost or bill rate than tasks that are less complex.   

The third factor provides the quantity of hours at that rate. In cases where a task covers two price periods, it is likely that the first part of the resource assignment for that task is costed and priced differently than the second portion of the task. The effort estimate on each resource assignment is a complex value stored with the daily distribution of effort per day.

For detailed instructions about how to set up custom attributes of work and resources as pricing and costing dimensions, see [Pricing Dimensions overview](../pricing-costing/pricing-dimensions-overview.md).

The financial estimate on each resource assignment is calculated as **rate/hr for the assignment multiplied by the number of hours.**  Similar to the effort estimate, the financial estimate for cost and revenue for each resource assignment is a complex value stored with the daily distribution of monetary amount per day. 

## Summarizing financial estimates for time
A financial estimate for time on a leaf node task is the sum of the financial estimates on all resource assignments for that task.

A financial estimate for time on a summary or parent task is the sum of the financial estimates on all of its child tasks. This is the estimated labor cost on the project. 

![Resource Estimates.](./media/navigation12.png)

## Default cost price and cost currency

The default cost price comes from the price lists attached to the contracting unit of the project. The cost currency of a project is always the currency of the contracting unit of the project. On a resource assignment, the financial estimate for cost is stored in the cost currency of the project. Sometimes, the currency in which the cost rate is set up in the price list is different from the project's cost currency. In these cases, the application converts the currency in which the cost price is set up for the currency of the project. On the **Estimates** grid, all cost estimates are displayed and summarized in the project's cost currency. 

## Default bill rate and sales currency

The default sales price comes from the project price lists attached to the related project contract if the deal is won, or from the related project quote if the deal is still in the pre-sales stage. The sales currency of the project is always the currency of the project quote or the project contract. On a resource assignment, the financial estimate for sales is stored in the sales currency of the project. Unlike cost, the sales price that is set up in the price list can never be different from the project's sales currency. There is no scenario where currency conversion is needed. On the **Estimates** grid, all sales estimates are displayed and summarized in the project's sales currency. 

## Performance improvements on Price Estimates

The calculation of role price estimates on a project task depends on a number of parameters like resource(s) assigned to the task, task duration, start and end dates and the number of tasks in the project. The time taken to perform price estimation calculations can vary depending on any changes made to any of the above, and the number of tasks in the project and associated parameters that were altered. This in turn can impact the user experience where they may see the estimates grid taking a longer time to load.  

To address this issue, we have introduced an option to price estimates on demand , which will yield higher performance gains, and in turn render a much better user experience. With this feature, customers can choose whether they want to price the estimates in **real-time** or **on-demand** per their need. 

Real time pricing will continue to keep the current behaviour to calculate and default the price estimates as soon as - 
  project tasks are created with start date and duration/end date , 
  project tasks are deleted, 
  or the duration on tasks with resource assignments is changed.  
**On demand pricing** will not update the price estimates immediately when any of the above actions are done. 
After making any changes to tasks in the project tasks grid , to see price estimates, users must click on **update prices** to view the cost and sales estimates.  

During performance tests on a standard environment, for a project with 30 tasks, and 1 dependency per task, in comparing with real time pricing, using on-demand pricing, we observed a performance gain of- 
  105% for updates on task duration
  110% for changes to task start date
  70% for copy project 

The feature can be configured under **Parameters -> Estimate Pricing Options -> On-Demand pricing**. The default option is **real time pricing**.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
