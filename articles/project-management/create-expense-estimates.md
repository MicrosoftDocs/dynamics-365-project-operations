---
title: Financial estimates for expenses on projects
description: This topic provides information about defining or estimating project-based expenses.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Financial estimates for expenses on projects
_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations allows Project managers to define project-based expenses for each project or a task. Each expense item can be associated with a specific project task. Expenses are categorized into different Expense categories which are defined at the organizational level. Pricing and costing for each expense category is defined in the price list. 

Complete the following steps to view, add, or delete a project expense.

1. Go to **Projects**, and select the project you want to work on.
2. Select the **Project Estimates** tab and view the list of project expenses.
3. Select **New Expense** to add an expense. Or, select an expense to delete, and then select **Delete Expense**.

The following attributes are defined for each expense line item:

- **Category**: The common groupings used to describe all expenses incurred on a project.
- **Start Date**: The date when the expense is forecasted to be incurred.
- **Quantity**: The estimated number of expense items for a specific category.
- **Unit Cost Price**: The unit price used to calculate to cost of the expense.
- **Unit Sales Price**: The unit price used to calculate the sale prices of the expense.
| **Field** | **Relevance, purpose and guidance** | **Downstream impact** |
| --- | --- | --- |
| Task | Shows a list of tasks in the project. This includes Summary and leaf node tasks | Selecting a task for an expense estimate line will impact the Estimated Expense Cost and Estimated Expense Sales at the Task levelLeaving the Task field empty, will result in the expense estimate to be tracked and summarized only at the project level |
| Category | Shows a list of transaction categories that have linked Expense categories in the application. | Selecting a category drives pricing and costing on the expense estimate line |
| Start date | User should enter the date that they forecast to incur the expense. |
 |
| Unit group | This is defaulted to the Unit Group that is setup as default on the selected Category.User may also change the selection to pick any other unit group |
 |
| Unit | This is defaulted to the Unit that is setup as default on the selected Category.User may also change the selection to pick any other unit. | Changing the unit will result in a different unit price and cost to get defaulted. |
| Quantity | Quantity of the expense that the user is estimating to incur |
 |
| Unit Cost | Cost of the selected category and unit combination as setup in the applicable cost price list | Unit Cost is always shown in the Project&#39;s cost currency |
| Unit Price | Price of the selected category and unit combination as setup in the applicable sales price list | Unit Price is always shown in the Project&#39;s sales currency |
| Total Cost | Cost Amount calculated as Quantity \* Unit Cost | Cost Amount is always shown in the Project&#39;s cost currency |
| Total Sales | Sales Amount calculated as Quantity \* Unit Price | Sales Amount is always shown in the Project&#39;s sales currency |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
