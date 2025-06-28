---
title: Financial estimates for resource time on projects
description: This article provides information about how financial estimates for time are calculated.
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Financial estimates for resource time on projects

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

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

The default sales price comes from the project price lists attached to the related project contract if the deal is won, or from the related project quote if the deal is still in the pre-sales stage. The sales currency of the project is always the currency of the project quote or the project contract. On a resource assignment, the financial estimate for sales is stored in the sales currency of the project. Unlike cost, the sales price that is set up in the price list can never be different from the project's sales currency. There's no scenario where currency conversion is needed. On the **Estimates** grid, all sales estimates are displayed and summarized in the project's sales currency.

## Performance improvements in Estimates pricing

The calculation of role price estimates on a project task depends on several parameters, such as the resources that are assigned to the task, the task duration, the start dates, and the end dates. The time that's required for price estimation calculations can vary, depending on changes that are made to any of these parameters and the number of tasks in the project. The calculation time can, in turn, increase the time that's required to process the estimates grid, and can therefore affect the user experience.

To address this issue, we've introduced an option to price estimates *on demand*. This option improves performance and the user experience. You can configure it at **Parameters \> Estimate Pricing Options \> On-Demand pricing**. At any point, admins can switch back to the default option, **Real-time pricing**. Estimates will then be priced in real time from that point onward.

The **Real-time pricing** option keeps the existing system behavior for calculating price estimates and entering default price estimates. Use this option in the following circumstances:

- Project tasks that have resource assignments are created, and have a start date and a duration/end date.
- Project tasks that have resource assignments are deleted.
- The task duration is changed on a project task that has resource assignments.

Use the **On demand pricing** option if you don't have to update the price estimates immediately when any of the preceding project task actions are performed.

When **On demand pricing** is configured, role prices aren't automatically retrieved for tasks that have resource assignments. Instead, they are set to **0.00** by default. To view the cost and sales price estimates for these tasks, users must select the **Update prices** option in the **Estimates** grid. 

> [!NOTE]
> In both real-time pricing and on-demand pricing, updates to the quantity field will cause the amount fields to be automatically updated if there's already a role price on record.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
