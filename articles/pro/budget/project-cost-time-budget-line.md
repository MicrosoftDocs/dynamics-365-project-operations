---
title: Project time budget lines
description: This article explains how to create project cost and sales time budget lines.
author: niranjanmaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project time budget lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains how to create budget lines for the **Time** transaction class. 

> [!NOTE]
> The steps that are outlined in this article apply to both cost budget lines and sales budget lines. The **Context** field of the budget line determines whether you're working with a cost budget line or a sales budget line.

A project budget has budget lines that are a snapshot of the budgeted quantity and amount. Project budget lines can be created under three transaction classes:

- A **Time** budget line tracks the recorded and approved time of bookable resources against the project.
- A **Material** budget line tracks the consumed materials that are approved against the project.
- An **Expense** budget line tracks the approved expenses against the project.

> [!NOTE]
> Budget dimensions should be unique across all budget lines. You can't create multiple budget lines that have the same dimensions.
>
> The dimensions that are considered for comparison are defined in the budget line match priority table. For more information, see [Budget line match priority](budget-line-match-priority.md).

## Create a Time budget line

**Prerequisite:** A project budget must be created for the project. For more information, see [Create and delete project cost budgets](create-delete-project-budget.md) or [Create and delete project sales budgets](create-delete-project-sales-budget.md).

To create a project budget line for the **Time** transaction class, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create the **Time** budget line for. Because a project budget was previously created, the **Budget** tab should be visible.
1. Select **New Project Budget Line** to create a budget line. A quick create dialog box appears. By default, the **Transaction class** field is set to **Time**.
1. Update all the fields in the dialog box according to the table that follows.
1. When you've finished, select **Save & Create New** to create another budget line, or select **Save & Close** to save your changes and close the quick create dialog box.
1. You can edit budget line fields in the grid on the **Budget** tab. Changes are saved when you select the **Tab** key to move to the next line in the grid. Edits can be made only until the budget is submitted for approval.

The following table explains how to set the fields in the quick create dialog box to create a **Time** budget line.

| Field | Requirement | Description |
|---|---|---|
| Context | Mandatory | Select the type of budget line that you want to create: **Cost** or **Sales**. |
| Transaction Class | Mandatory | Leave the default value, **Time**. |
| Description | Optional | Enter a description of the budget line. For example, enter **Time for design task** or **Time for foundation activity**. |
| Start Date | Mandatory |<p>Specify the start date for the budget line. The specified date must be between the start date and end date of the project. By default, this field is set to the start date of the project.</p><p>Together, this field and the **End Date** field define the period when the actuals of the projects are tracked against the budget line.</p> |
| End Date | Mandatory | <p>Specify the end date for the budget line. The specified date must be between the start date and end date of the project. By default, this field is set to the end date of the project.</p><p>Together, this field and the **Start Date** field define the period when the actuals of the projects are tracked against the budget line.</p> |
| Task | Optional | If you want to track the budget against a specific task of the project, select the task. To track the budget against all tasks of the project, leave this field blank. |
| Role | Optional | If you want to track the budget against a specific role of the organization, select the role. To track the budget against all roles of the organization, leave this field blank. |
| Resource | Optional | If you want to track the budget against a specific bookable resource for the selected task or role, select the resource. If you didn't select a task in the **Task** field or a role in the **Role** field, you can select a resource that isn't assigned to any role or a task by selecting **Search**. To track the budget against all bookable resources, leave this field blank. |
| Resourcing Unit | Optional | If you want to track the budget against a specific resourcing unit, select the resourcing unit. If you selected a resource in the **Resource** field, the resourcing unit that you select must be aligned with the resourcing unit of that resource. If you didn't select a resource, select any resourcing unit that you want to track the budget against. To track the budget against all resourcing units, leave this field blank. By default, this field is blank. |
| Cost Source | Optional | Select **Internal** to track the costs where the cost source is internal. Select **External** to track the costs from a vendor or subcontractor. To track the costs from any cost source, leave this field blank. By default, this field is blank. |
| Vendor Name | Optional | If you selected **External** in the **Cost Source** field, select the vendor or subcontractor to track the costs from. To track the costs from any vendor or subcontractor, leave this field blank. By default, this field is blank. |
| Quantity | Optional | Specify the quantity to budget for the selected dimensions for time, materials, and expenses. The actual quantity is tracked against the budgeted quantity only if the budget line has a quantity. If the quantity is left blank, only the amount is tracked against the dimensions of the budget line. By default, this field is blank. |
| Unit Group | Optional | For the **Time** transaction class, this field is set to **Time** for the budget line, and the value can't be changed. |
| Unit | Optional | <p>Select a unit that belongs to the **Time** unit group.</p><p><strong>Note:</strong> Only the units from the selected unit group are available for selection.</p> |
| Unit Price | Optional | The unit price is the price of single-unit quantities of time, materials, or expenses. To have the unit price from the price list calculated based on the selected dimensions, if it's available in the system, select **Save & Close**. You can override and update the default unit price if you want to track against a specific unit price. |
| Currency | Mandatory | To get the currency from the price list, based on the selected dimensions, select **Save & Close**. You can update the value to any other currency that you want to budget for. In this case, the currency conversion applies when the system tracks whether the actual currency differs from the budgeted currency for the selected dimensions. By default, this field is set to the organization currency. |
| Amount | Mandatory | If you set the **Quantity** field, the amount is calculated as *Quantity* &times; *Unit price*. If you didn't set the **Quantity** field, enter the amount to budget against the selected dimensions of the budget line. The value must be a positive nonzero number. |
| Contingency | Optional | Enter the contingency amount to add to the budgeted amount. The budget for the selected dimensions is calculated as *Amount* + *Contingency*. This field isn't applicable if the **Context** field is set to **Sales**. |
| Budget | Mandatory | The budget for the budget line for the selected dimensions. This field is automatically set based on the dimensions. The value is calculated as *Amount* + *Contingency*. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
