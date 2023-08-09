---
title: Create budget lines from unmatched actuals
description: This article explains how to create project budget lines from cost actuals which could not be matched to an existing budget lines during revision. 
author: niranjanmaski
ms.date: 28/07/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create budget lines from unmatched actuals

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article outlines the process of creating budget lines from unmatched cost actuals. This can occur when actuals don't match existing budget lines based 
on dimensions or defined budget match priorities. It's also possible due to unforeseen actuals during budget creation and approval.

This feature allows users to create budget lines that correspond to unmatched cost actuals. 
This choice is available when revising an approved budget line.

## How to see cost actuals unmatched to a budget line

After a project budget is approved, all approved cost actuals related to the project undergo automatic evaluation to match with the planned budget lines. 
This evaluation occurs periodically. To check the status of this evaluation, you can refer to the **Budget Evaluation Status** field on the Actual main form.

If a cost actual fails to match with a budget line, the evaluation status will show as **Completed**, and the **Budget Evaluation Result** field will display an error message 
indicating that a matching budget line for the actual could not be found. 

To simplify the process of identifying cost actuals that do not match with budget lines, two default views have been introduced. These views help users quickly locate cost actuals 
that have not been matched to an approved budget line.

Here's how to access these cost actual views:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Locate and click on the desired project to open the project main form.
1. If you don't find the **Actuals** tab listed, click on **Related** and then select the Actuals tab.
1. Within the Actuals tab, find the view selector drop-down at the top of the grid.
1. Two new views will be available: **Cost Actuals Matched to Budget** and **Cost Actuals Unmatched to Budget**.
1. The **Cost Actuals Unmatched to Budget** view will display the list of cost actuals that haven't been matched to an approved budget line.

> [!NOTE]
> Two new views on Actuals showing matched and unmatched actuals to a budget lines are also available on the Actuals list page as well.
> 

## Create budget lines from cost actuals unmatched to a budget line


To create a project budget line from the unmatched cost actuals, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.

2. Click on the **Budget** tab 
1. In the top ribbon bar click on the **Budget** and then select **Create budget period** from the drop-down menu.
1. The budget period configuration dialog for the selected project will open.
1. If an organization budget period configuration is set up, the **Fiscal start** and **Week starts on** will be taken from the organization budget period template. Otherwise, they will default to July and Monday.
1. The **Start year** and **Start month** will be defaulted to the project's start year and month.
1. The **End year** and **End month** will be defaulted to the project's end year and month.
1. You can edit the budget period configuration at the project level to meet your specific needs.
1. You can edit the budget period config at the project level as per your needs.
1. Refer to the table below for details of the fields.

there are no matching b for the **Time** transaction class.

A project budget has budget lines that are a snapshot of the budgeted quantity and amount. Project budget lines can be created under three transaction classes:

- A **Time** budget line tracks the recorded and approved time of bookable resources against the project.
- A **Material** budget line tracks the consumed materials that are approved against the project.
- An **Expense** budget line tracks the approved expenses against the project.

> [!NOTE]
> Budget dimensions should be unique across all budget lines. You can't create multiple budget lines that have the same dimensions.
>
> The dimensions that are considered for comparison are defined in the budget line match priority table. For more information, see [Budget line match priority](budget-line-match-priority.md).

## Create a Time budget line

**Prerequisite:** A project budget must be created for the project. For more information, see [Create and delete project cost budgets](create-delete-project-budget.md).

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
| Quantity | Optional | Specify the quantity to budget for the selected dimensions for time, materials, and expenses. The actual quantity will be tracked against the budgeted quantity only if the budget line has a quantity. If the quantity is left blank, only the amount will be tracked against the dimensions of the budget line. By default, this field is blank. |
| Unit Group | Optional | For the **Time** transaction class, this field is set to **Time** for the budget line, and the value can't be changed. |
| Unit | Optional | <p>Select a unit that belongs to the **Time** unit group.</p><p><strong>Note:</strong> Only the units from the selected unit group are available for selection.</p> |
| Unit Price | Optional | The unit price is the price of single-unit quantities of time, materials, or expenses. To have the unit price from the price list calculated based on the selected dimensions, if it's available in the system, select **Save & Close**. You can override and update the default unit price if you want to track against a specific unit price. |
| Currency | Mandatory | To get the currency from the price list, based on the selected dimensions, select **Save & Close**. You can update the value to any other currency that you want to budget for. In this case, the currency conversion will apply when the system tracks whether the actual currency differs from the budgeted currency for the selected dimensions. By default, this field is set to the organization currency. |
| Amount | Mandatory | If you set the **Quantity** field, the amount is calculated as *Quantity* &times; *Unit price*. If you didn't set the **Quantity** field, enter the amount to budget against the selected dimensions of the budget line. The value must be a positive non-zero number. |
| Contingency | Optional | Enter the contingency amount to add to the budgeted amount. The budget for the selected dimensions will be calculated as *Amount* + *Contingency*. |
| Budget | Mandatory | The budget for the budget line for the selected dimensions. This field is automatically set based on the dimensions. The value is calculated as *Amount* + *Contingency*. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
