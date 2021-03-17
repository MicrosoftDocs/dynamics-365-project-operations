---
title: Financial estimates for resource time on projects
description: This topic provides information about how financial estimates for time are calculated in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Financial estimates for resource time on projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Financial estimates for time are calculated based on 

a. Type of generic or named Team member assigned to each leaf node task (a task in the project plan that is at the lowest granularity ie. does not have any child tasks) on the project plan. 

b. The type or complexity of work

c. The spread of effort for that resource's assignment on the task 

The **first 2 factors** influence the unit cost or bill rate of a resource's assignment. Unit cost or bill rate of a resource assignment is determined by the attributes of the resource assigned such as the Oraganizational unit to which the resource belongs and the standard role of the resource. You can also add custom attributes relevant to your business for the resource like say, Standard title or Experience level etc and have them to influence the unit cost/ bill rate of the assignment.
In addition to the attributes of the resource, attributes of work ie. the task also influence the unit bill rate or cost rate of the assignment. Examples could be say, Complexity of work where certain tasks are more complex and so that same resource's assignment on such a task has a higher unit cost or bill rate than on another task that is not as complex.   

The **third factor** provides the quantity of hours at that rate. In some cases where a task is crossing 2 price periods, it is likely that the first part of the resource assignment for that task is costed and priced differently using a different price list than the 2nd portion of the task. The effort estimate on each resource assignment is a complex value stored with the day wise distribution of effort per day. 
For detailed instructions on how to setup custom attributes of work and resources as pricing/costing dimensions, please follow the topics in  [Pricing Dimensions overview](../pricing-costing/pricing-dimensions-overview.md)

The financial estimate on each resource assignments are calculated as **rate/hr for the assignment multiplied by the number of hours.**  Similar to effort estimate, the finacial estimate for cost and revenue for each resource assignment is a complex value stored with the day wise distribution of monetary amount per day. 
A financial estimate for time on the leaf node task is a sum of the financial estimates on all resources assignments on that task
A financial estimate for time on a summary or parent task is the sum of the financial estimates on all of its child tasks. This in turn, adds up the estimated labor cost on the project. 

![Resource Estimates](./media/navigation12.png)

## Default cost price and cost currency

Cost prices are defaulted from the price list attached to the Contracting Unit on the project. The currency of the Project is always the currency of the Contracting Unit of the Project. On the resource assignment, the financial estimate for cost is stored in the currency of the project. Sometimes, it is possible that the currency in which the cost rates is setup in the price list is different from the project's currency. In these cases, the application converts the currency in which the cost price is setup to the currency of the Project. And all cost estimates are always displayed and summarized in the Project's currency. 

## Default bill rate and sales currency

Sales prices are defaulted from the project price list attached to the related Prject Contract if the deal is won or from the related Project Quote of the deal is still in pre-sales stage. The **Sales** currency of the Project is always the currency of the Project Quote or the Project Contract. On the resource assignment, the financial estimate for sales is stored in the **Sales** currency of the project. Unlike cost, sales price setup in the price list can never be different from the project contract's currency. So there is no scenario where currency conversion is needed. All **sales** estimates for time on a Project are always displayed and summarized in the Project Contract's currency. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
