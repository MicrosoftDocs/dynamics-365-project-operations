---
title: Financial estimates for expenses on projects
description: This article provides information about defining or estimating project-based expenses.
author: poojafandan
ms.date: 01/22/2025
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Financial estimates for expenses on projects

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing._

Dynamics 365 Project Operations allows Project managers to define project-based expenses for each project or a task. Each expense item can be associated with a specific project task. Expenses are categorized into different expense categories, which are defined at the organizational level. Pricing and costing for each expense category is defined in the price list. 

Complete the following steps to view, add, or delete a project expense.

1. Go to **Projects**, and select the project you want to work on.
1. Select the **Project Estimates** tab and view the list of project expenses.
1. Select **New Expense estimate** to add an expense. Or, select an expense to delete, and then select **Delete Estimate Line**.

> [!NOTE]
> **The Project estimate updates feature is now in Preview.**
>
> Once the **Project estimate updates** feature is enabled, it can't be disabled. These updates include label changes at the project level where the original **Estimates** tab shows **Time phased estimates**, and the newly labeled **Estimates** tab is a consolidated view of expense and material estimates. The new grid for expense and material estimates allows easy creation and editing of those estimates.
>
>To enable the **Project estimate updates** feature, follow these steps.
>
>1. Go to **Settings** \> **Parameters**.
>1. Open the **Parameters** record.
>1. On the Action Pane, on the **Feature Control** tab, select **Project estimate updates**.
>1. In the confirmation dialog box, select **OK**.
>1. After a few moments, refresh your browser. The feature capabilities are available, and the feature is removed from the list of features to be enabled. 

The following table provides information about the fields on the **Expense Estimate line** on a Project. 


| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Task | A list of tasks in the project. This list includes summary and leaf node tasks. | Selecting a task for an expense estimate line impacts the estimated expense cost and estimated expense sales for a task. If this field is left empty, the expense estimate is tracked and summarized only at the project level. |
| Category | A list of transaction categories that have linked expense categories in the application. | Selecting a category drives pricing and costing on the expense estimate line. |
| Start date | The forecasted date on which the expense occurs. | There isn't a downstream impact for this field. |
| Quantity | The quantity of the estimated expense you incur. | There isn't a downstream impact for this field. |
| Unit group | The default value in this field comes from the unit group set up as default on the selected category. You can update this field to select another unit group. | There isn't a downstream impact for this field. |
| Unit | The value in this field defaults to the default unit of the selected category. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Price | The cost price of the selected category and unit combination as set up in the applicable cost price list. | The unit cost is always shown in the project's cost currency. |
| Amount| Amount represents the total cost of an estimated expense. It's calculated as Price × Quantity. | The unit cost amount is always shown in the project's cost currency. |
| Price(Sales) | The sales price of the selected category and unit combination as set up in the applicable sales price list. | The unit sales are always shown in the project's sales currency. |
| Amount(Sales) | Amount(Sales) represents the total sales amount of the estimated expense. It's calculated as Price(Sales) × Quantity. | The unit sales amount is always shown in the project's sales currency. |

> [!NOTE]
The grid allows in-line editing with the first line of the estimate being in cost context, which is always shown in the project's cost currency. The grid doesn't allow in-line update of the sales price in the first line of the estimate line. When you select the chevron, the grid expands to a child row which provides where the sales price can be edited. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
