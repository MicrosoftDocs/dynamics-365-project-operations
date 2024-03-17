---
title: Financial estimates for expenses on projects
description: This article provides information about defining or estimating project-based expenses.
author: rumant
ms.date: 03/19/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Financial estimates for expenses on projects
_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations allows Project managers to define project-based expenses for each project or a task. Each expense item can be associated with a specific project task. Expenses are categorized into different expense categories, which are defined at the organizational level. Pricing and costing for each expense category is defined in the price list. 

Complete the following steps to view, add, or delete a project expense.

1. Go to **Projects**, and select the project you want to work on.
2. Select the **Project Estimates** tab and view the list of project expenses.
3. Select **New Expense** to add an expense. Or, select an expense to delete, and then select **Delete Expense**.



> [!NOTE]
> **Now in Preview: Project estimate updates feature**

> A new feature labeled Project estimate updates is currently in Preview. Once the **Enable Project estimate updates** feature is enabled, it can't be disabled. These updates include label changes at the Project level where now the original Estimates tab is showing Time phased estimates, and the newly labeled Estimates tab is a consolidated view of Expense and Material Estimates. The new grid for Expense and Material estimates allows easy creation and editing of those estimates.

>To enable the **Project estimate updates** feature, follow these steps.

>1. Go to **Settings** \> **Parameters**.
>1. Open the **Parameters** record.
>1. On the Action Pane, on the **Feature Control** tab, select **Project estimate updates**.
>1. In the confirmation dialog box, select **OK**.
>1. After a few moments, refresh your browser. The feature capabilities will now be available and the feature will be removed from the list of features to be enabled. 

The following table provides information about the fields on the **Expense Estimate line** on a Project. 

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Task | A list of tasks in the project. This includes summary and leaf node tasks. | Selecting a task for an expense estimate line will impact the estimated expense cost and estimated expense sales for a task. If this field is left empty, the expense estimate is tracked and summarized only at the project level. |
| Category | A list of transaction categories that have linked expense categories in the application. | Selecting a category drives pricing and costing on the expense estimate line. |
| Start date | The forecasted date on which the expense will occur. | There is no downstream impact for this field. |
| Unit group | The default value in this field comes from the unit group that's set up as default on the selected category. You can update this field to select another unit group. | There is no downstream impact for this field. |
| Unit | The value in this field defaults to the default unit of the selected category. You can update this field to select another unit. | Changing the unit results in a different default unit price and cost. |
| Quantity | The quantity of the estimated expense you will incur. | There is no downstream impact for this field. |
| Unit Cost | The cost of the selected category and unit combination as set up in the applicable cost price list | The unit cost is always shown in the project's cost currency. |
| Unit Price | The price of the selected category and unit combination as setup in the applicable sales price list. | The unit price is always shown in the project's sales currency. |
| Total Cost | The cost amount that is calculated as quantity \* unit cost.| The cost amount is always shown in the project's cost currency. |
| Total Sales | The sales amount that is calculated as quantity \* unit price. | The sales amount is always shown in the project's sales currency. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
