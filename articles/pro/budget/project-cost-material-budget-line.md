---
title: Project material budget line
description: This article explains how to create project cost material budget line.
author: niranjanmaski
ms.date: 03/13/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project material budget line.

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to create a budget line for the transaction class Material.

A project budget has budget lines that are a snapshot of the budgeted quantity and amount.

Project budget lines can be created under three transaction classes:

- A **Time** budget line tracks the recorded and approved time of bookable resources against the project.
- A **Material** budget line tracks the consumed materials that are approved against the project.
- An **Expense** budget line tracks the approved expenses against the project.

> [!Note]
> Budget dimensions should be unique across all budget lines. You can't create multiple budget lines that have the same dimensions.

## Create a Material budget line

**Prerequisite:** A project budget must be created for the project. For more information, see [Create and delete project cost budgets](create-delete-project-budget.md).

To create a project budget line for the **Material** transaction class, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create the **Material** budget line for.

    Because a project budget was previously created, the **Budget** tab should be visible.

1. Select **New Project Budget Line** to create a budget line.

    A quick create form appears. By default, the **Transaction class** field is set to **Time**.

1. Update all the fields in the form according to the table that follows.
1. When you've finished, select **Save & Create New** to create another budget line, or select **Save & Close** to save the details and close the quick create form.
1. You can edit budget line fields in the grid on the **Budget** tab. Changes are saved when you select the **Tab** key to move to the next line in the grid. Edits can be made only until the budget is submitted for approval.

The following table explains how to set the fields in the quick create form to create a **Material** budget line.

| Field | Requirement | Description |
|---|---|---|
| Transaction Class | Mandatory | Select **Material**. |
| Description | Optional | Enter a description of the budget line. For example, enter **Budget for laptops** or **Budget for bricks**. |
| Start Date | Mandatory | <p>Specify the start date for the budget line. The specified date must be between the start date and end date of the project. By default, this field is set to the start date of the project.</p><p>Together, this field and the **End Date** field define the period when the actuals of the projects are tracked against the budget line.</p> |
| End Date | Mandatory | <p>Specify the end date for the budget line. The specified date must be between the start date and end date of the project. By default, this field is set to the end date of the project.</p><p>Together, this field and the **Start Date** field define the period when the actuals of the projects are tracked against the budget line.</p> |
| Task | Optional | If you want to track the budget against a specific task of the project, select the task. To track the budget against all tasks of the project, leave this field blank. |
| Select Product | Optional | Select **Existing** to budget for an existing product in the organization. Select **Write-In** to budget for a write-in product. |
| Write in Product | Optional | <p>If you selected **Write-In** in the **Select Product** field, enter the name of the product to budget for.</p><p><strong>Note:</strong> Entry of a new write-in product on the budget line doesn't create a new product in the list of products for the organization.</p><p>Matching of actual material use against this budget line occurs only if the product that's in actual material use exactly matches the product of the budget line, together with other dimensions.</p> |
| Product | Optional | If you selected **Existing** in the **Select Product** field, select the product to budget for. By default, this field is blank. |
| Cost Source | Optional | Select **Internal** to track the costs where the cost source is internal. Select **External** to track the costs from vendor or subcontractor. To track the costs from any cost source, leave this field blank. By default, this field is blank. |
| Vendor Name | Optional | If you selected **External** in the **Cost Source** field, select the vendor or subcontractor to track the costs from. To track the costs from any vendor or subcontractor, leave this field blank. By default, this field is blank. |
| Quantity | Optional | Specify the quantity to budget for the selected dimensions for **Time**, **Material**, and **Expense**. The actual quantity will be tracked against the budgeted quantity only if the budget line has a quantity. If the quantity is left blank, only the amount will be tracked against the dimensions of the budget line. By default, this field is blank. |
| Unit Group | Optional | If **Select Product** is **Existing**, **Unit group** is defaulted from the unit group of the selected product. </br> If **Select Product** is **Write-In**, you can pick the suitable **Unit group** for the product from the list of unit groups in the drop down.|
| Unit | Optional | If **Select Product** is **Existing**, **Unit** is defaulted from the unit of the selected product. </br> If **Select Product** is **Write-In**, you can pick the suitable unit for the product from the list of units in the selected **Unit-group**. </br> If you choose to pick a unit, other than the list of units displayed in drop down for the selected **Unit group**, the **Unit group** field is cleared to pick the right **Unit group** for the selected **Unit**. |
| Unit Price | Optional | The unit price is the price of single-unit quantities of **Time**, **Material**, or **Expense**. To have the unit price from the price list calculated based on the selected dimensions, if it's available in the system, select **Save & Close**. You can override and update the default unit price if you want to track against a specific unit price. |
| Currency | Mandatory | To get the currency from the price list, based on the selected dimensions, select **Save & Close**. You can update the value to any other currency that you want to budget for. In this case, the currency conversion will apply when the system tracks whether the actual currency differs from the budgeted currency for the selected dimensions. By default, this field is set to the organization currency. |
| Amount | Mandatory | If you set the **Quantity** field, the amount is calculated as *Quantity* &times; *Unit price*. If you didn't set the **Quantity** field, enter the amount to budget against the selected dimensions of the budget line. The value must be a positive non-zero number. |
| Contingency | Optional | Enter the contingency amount to add to the budgeted amount. The budget for the selected dimensions will be calculated as *Amount* + *Contingency*. |
| Budget | Mandatory | The budget for the budget line for the selected dimensions. This field is automatically set based on the dimensions. The value is calculated as *Amount* + *Contingency*. |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
