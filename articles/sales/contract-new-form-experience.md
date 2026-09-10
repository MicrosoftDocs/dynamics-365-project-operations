---
title: Modern contract experience (preview)
description: Create, review, and manage project contracts with the modern contract experience in Dynamics 365 Project Operations. See how every tab helps you act faster.
author: poojafandan
ms.date: 09/10/2026
ms.topic: concept-article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Modern contract experience (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The modern contract experience in Dynamics 365 Project Operations provides a form for creating, reviewing, and managing project contracts. It brings contract financials, billing progress, actuals, contract lines, and health indicators into focused views so that you can identify contracts and lines that need attention.

The experience includes a project contracts list, a quick-create panel, and a contract form with the following tabs:

- **Overview**
- **Contract Lines**
- **Analysis**
- **Details**
- **Advances and Retainers**

> [!NOTE]
> The columns, commands, and actions that you see can vary based on your security role, the contract status, and how your organization configured Project Operations.

## Work with the modern project contracts list

The modern project contracts list is a financial and health-monitoring workspace. In addition to contract identity, customer, and status, the list surfaces the account manager, contracted amount, budget variance, current gross margin, NTE status, and overall contract health. You can identify contracts that need attention without opening each record.

Use the keyword filter to find a contract, select a column heading to sort the list, or select a linked contract, customer, or account manager to open the related record. Status and health values use badges and visual indicators so that you can scan the list quickly.

Each row also includes an expand control. Expand a contract to review its project lines and line-level financial and health information while remaining on the contracts list.

### Select a view

Use the view selector to choose the contracts that you want to review.

| View | Description |
| ------ | ------------- |
| **My project contracts** | Contracts assigned to you. |
| **All contracts** | All project contracts that you have permission to view. |
| **Draft** | Contracts that are being prepared. |
| **Confirmed** | Contracts that are confirmed. |
| **Completed** | Contracts for which the work is complete. |
| **On hold** | Contracts that are temporarily paused. |
| **Canceled** | Contracts that you canceled. |
| **Change orders** | Change orders across project contracts. |

### Use command bar actions

The command bar provides the following actions:

- **New contract**
- **Refresh**
- **Edit**
- **Copy**
- **Delete**
- **Assign**
- **Share**
- **Email a link**

You can find more commands in the overflow menu. These commands include focused view, charts, visualizations, flows, reports, Excel templates, Excel import and export, and dashboards.

The availability of a command depends on the selected contract, its status, and your permissions.

### Review contract information

The **My Project Contracts (Modern)** view includes the following information:

| Column | Description |
| -------- | ------------- |
| **Contract** | The contract name. Select the link to open the Contract form. |
| **Contract status** | Shows whether the contract is Draft, Confirmed, Completed, On hold, or Canceled. |
| **Contract status reason** | Provides more detail about the current contract status. |
| **Customer** | The customer associated with the contract. Select the link to open the customer record. |
| **Account manager** | The person responsible for the customer relationship. Select the link to open the user or resource record. |
| **Contracted amount** | The total value committed across the contract lines. |
| **Budget variance** | The customer budget minus the billed amount. |
| **Current gross margin** | Shows the current contract margin as a percentage and visual indicator. The indicator shows whether margin is meeting expectations. |
| **NTE status** | Shows whether the contract is within or over its not-to-exceed (NTE) limit. |
| **Contract health** | Shows the overall health as a badge, such as **On track**. Select the value to open the contract's **Analysis** tab and review the contributing signals. |

Use the selection checkboxes to select one or more contracts. Select the expand control for a contract to review its project lines in the nested grid.

### Review project lines from the list

The expanded grid includes the following information for each project line:

| Column | Description |
| -------- | ------------- |
| **Line name** | Opens the contract line. |
| **Project** | Opens the associated project. |
| **Billing method** | Shows Time and Material or Fixed Price. |
| **Invoice schedule** | Shows the billing schedule, such as monthly, milestone, or progress-based. |
| **Transaction classes** | Shows the transaction classes included on the line. |
| **Margin %** | Shows the line margin and its health indicator. |
| **Contract value** | The contracted value of the line. |
| **Budget variance** | Compares the line's project budget and financial progress. |
| **NTE status** | Shows the line's NTE utilization and status. |
| **Change order** | Shows the related change order and its status. |
| **Line health** | Shows whether the line is On track or Off track. |

## Create a project contract

Select **New contract** on the project contracts list to open the contract pane. The pane lets you enter the information required to start a contract without navigating away from the list.

Enter the following information:

| Field | Description |
| ------- | ------------- |
| **Name** | The contract name. This field is required. |
| **Customer** | The customer for the contract. |
| **Contracting unit** | The business unit responsible for delivering and administering the contract. |
| **Account Manager** | The person responsible for the customer relationship. |
| **Opportunity** | The originating opportunity, when applicable. |
| **Quote** | The originating quote, when applicable. |
| **Product price list** | The price list used for product-based contract lines. |
| **Owning company** | *Project Operations Integrated with ERP only.* The legal entity that owns the contract. This field is required and determines the financial dimensions, currency, and posting rules applied to the contract. |
| **Currency** | The currency used to price and bill the contract. |
| **NTE limit** | The overall not-to-exceed amount for the contract, when applicable. |
| **Delivery date** | The date by which the contracted work is expected to be delivered. |

To create the contract and continue working on the form, select **Save and add details**. To create the contract and return to the list, select **Save and close**. Select **Cancel** to close the pane without creating a contract.

## Overview tab

The **Overview** tab is a financial and billing workspace. It brings contract KPIs, contract-line health, billed and unbilled actuals, and the timeline into one page. You can understand the contract's current position and complete common billing tasks without navigating to another tab.

The form header keeps the contract name, customer, contracting unit, owner, and status visible while you work.

### Review financial KPIs

The **Financial** section at the top of the tab shows the overall contract health badge and the time when the financial information was last updated. Actuals-based key performance indicators (KPIs) summarize the contract:

| KPI | Description |
| ----- | ------------- |
| **Contract value** | The total value of the project contract. |
| **Billed amount** | The total sales amount of billed time, material, and expense transactions that are posted to customer invoices. The total unbilled amount appears below it for comparison. |
| **Unbilled amount** | The total sales amount of time, material, and expense transactions from the invoiceable backlog that aren't yet billed. |
| **Cost incurred** | The actual costs posted against the contract. Expected cost appears below it for comparison. |
| **Gross margin** | The current actual margin on recognized revenue. |

The following calculations are used:

- Actual margin percentage = `(Billed amount - Cost incurred) / Billed amount`
- Expected margin percentage = `(Contract value - Estimated cost) / Contract value`

Percentages are calculated when the denominator has a value.

### Review project contract line health

The **Project contract line health** grid shows the financial and billing position of each contract line. Use this grid to identify lines that need attention and to open billed or unbilled transactions directly from the **Overview** tab.

| Column | Description |
| -------- | ------------- |
| **Line** | The contract line name. Select the link to open the line. |
| **Billing method** | Time and Material or Fixed Price. |
| **NTE** | The percentage of the not-to-exceed limit that you consumed. |
| **Gross margin** | The current actual margin for the line. |
| **Expected margin** | The expected margin based on the line value and estimated cost. |
| **Budget consumption** | The percentage of the approved project budget that you consumed. |
| **Remaining budget** | The percentage of the approved project budget that remains. |
| **Billed actuals** | The billed sales amount for the line. Select the amount to see the actuals that you billed. |
| **Unbilled actuals** | The unbilled sales amount for the line. Select the amount to review and prepare actuals for invoicing. |
| **Line health** | Shows the line's health, such as **On track** or **Off track**. |

When you select a contract line, you can use the actions available for that line, including generating an invoice schedule, generating a schedule of values, and importing project estimates.

### Understand health badges

The contract and line health badges summarize signals such as margin, cost performance, budget consumption, billing progress, and NTE utilization. The badges help you identify a potential issue without reviewing every underlying transaction.

> [!IMPORTANT]
> Administrators can configure the threshold values that the health badges use in the Power Platform admin center. As a result, the conditions that produce an **On track**, **At risk**, or **Off track** badge can differ between environments. For steps to customize the grid health badges, see [Customize health badges in the modern contract experience](customize-health-badge-modern-contract.md).

### Review billed and unbilled actuals

The values in the **Billed actuals** and **Unbilled actuals** columns are links.

Select **Billed actuals** to open the billed transactions for the contract line. You can see which time, expense, material, or fee actuals contributed to the billed amount without leaving the contract.

Select **Unbilled actuals** to open the unbilled transactions for the line. From the same experience, you can review eligible actuals and mark them as **Ready to invoice**. You don't have to navigate out of the contract.

| Column | Description |
| -------- | ------------- |
| **Billing status** | Shows whether the transaction is Not ready to invoice, Ready to invoice, Billed, or Non-chargeable. |
| **Transaction date** | The date when the actual was posted. |
| **Resource / Role** | The resource and role category associated with the transaction. |
| **Transaction class** | Time, Expense, Material, or Fee. |
| **Quantity / Hours** | The units consumed. |
| **Unit cost / Rate** | The applicable cost or bill rate. |
| **Total cost** | The actual cost amount. |
| **Sales amount** | The billed or unbilled sales value. |

From the actuals panel, you can:

- Switch between unbilled sales time, expense, and material views.
- Filter by transaction class and billing status.
- Group transactions by resource, role, or period.
- Review total hours, cost, billed amount, and unbilled amount.
- Export the displayed transactions to a CSV file.
- Mark eligible unbilled actuals as **Ready to invoice**.

After the actuals are ready, select **Create invoice** on the contract command bar to create the invoice while remaining on the contract form.

### Use the timeline

The timeline is available at the bottom of the **Overview** tab. Use it to review and add notes, activities, and other contract-related interactions.

## Contract Lines tab

The **Contract Lines** tab is a full-page workspace for reviewing and managing all project-based contract lines. The full-width grid makes it easy to compare line setup, billing progress, actuals, and financial performance in one view.

Each row represents a contract line. Select the line name to open its details, or select the row to use the available line actions. The grid can include:

| Column | Description |
| -------- | ------------- |
| **Line name** | The contract line name. Select the link to open the line. |
| **Project** | The project that delivers the work. |
| **Included tasks** | Indicates whether the line includes all project tasks or selected tasks. |
| **Transaction classes** | The time, expense, material, or fee transactions included on the line. |
| **Billing method** | Time and Material or Fixed Price. |
| **Invoice schedule type** | The schedule used to invoice the line. |
| **Margin** | The current margin for the line. |
| **Contracted amount** | The agreed or estimated value of the line. |
| **Project budget** | The approved project budget associated with the line. |
| **Billed amount** | The amount already billed for the line. |
| **Cost incurred** | The actual cost posted against the line. |
| **Next billing event** | The next scheduled invoice or billing milestone. |
| **Unbilled actuals** | The amount that you didn't bill yet. |
| **NTE status** | The line's not-to-exceed utilization and status. |

The grid also shows rollups such as total actual hours, total actual cost, and total billed amount. Variance and status indicators help you identify lines where cost, budget consumption, billing, or NTE utilization requires attention.

Select a billed or unbilled amount to review the underlying actuals without leaving the contract.

### Manage contract lines

From the **Contract Lines** tab, you can:

- Create a project-based contract line.
- Open and edit an existing contract line.
- Delete an eligible contract line.
- Import estimates from the associated project.
- Generate an invoice schedule.

The available actions depend on the contract status, billing method, and your security role.

### Delete a contract line

To delete a line, select it in the grid, select **Delete**, and confirm the deletion.

Project Operations validates the contract line before deleting it. You can't delete a contract line in the following situations:

- The contract is in a status that makes its lines read-only.
- The contract line is linked to an existing invoice line.
- The contract line has related actuals in the billing backlog.

If the line can't be deleted, Project Operations displays a message that explains the blocking dependency. Preserve the line when it contains financial history, and use the applicable correction, reversal, or change-order process instead.

### Open and review a contract line

Select a contract line name in the grid to open the line and review its setup, financial information, NTE utilization, and related details. Project Operations opens the line in a full-page contract-line workspace. The line name appears in the header, and the **Summary** tab opens by default.

The **Summary** tab brings together the information that defines the line and its financial value. The screen uses three sections across the upper part of the page:

- The first section identifies the parent contract, line name, billing method, and associated project.
- The second section defines which project tasks and transaction classes are included.
- The third section shows the contracted amount, discounts, fees, estimated tax, extended amount, and customer budget.

The setup section includes:

| Field | Description |
| ------- | ------------- |
| **Contract** | The parent project contract. |
| **Name** | The name of the contract line. |
| **Billing method** | Time and Material or Fixed Price. |
| **Project** | The project that delivers the work. |
| **Included tasks** | Indicates whether the line includes all project tasks or selected tasks. |
| **Include time** | Indicates whether time transactions are included. |
| **Include expense** | Indicates whether expense transactions are included. |
| **Include material** | Indicates whether material transactions are included. |
| **Include fee** | Indicates whether fee transactions are included. |

The financial section includes:

| Field | Description |
| ------- | ------------- |
| **Contracted amount** | The agreed or estimated value of the contract line. |
| **Discount %** | The discount percentage applied to the line. |
| **Discount amount** | The calculated discount amount. |
| **Fee %** | The fee percentage applied to the line. |
| **Fee amount** | The calculated fee amount. |
| **Estimated tax** | The estimated tax for the line. |
| **Extended amount** | The line amount after the applicable discount, fee, and tax calculations. |
| **Customer budget** | The customer budget associated with the line. |

The NTE section spans the bottom of the Summary tab. It shows:

| Field | Description |
| ------- | ------------- |
| **Not-to-exceed limit** | The contractual maximum for the line. |
| **Spent amount** | The amount already consumed against the NTE limit. |
| **Committed amount** | The amount committed against the NTE limit. |
| **Remaining amount** | The amount still available under the NTE limit. |
| **Last updated** | The time when the spent or committed amount was last updated. |

Use the tabs across the top of the contract-line workspace to move between line setup and billing information:

| Tab | Use this tab to |
| ----- | ----------------- |
| **Summary** | Review line setup, financial values, and NTE consumption. |
| **Chargeable Tasks** | Specify which project tasks are chargeable for the line. |
| **Chargeable roles** | Manage chargeability for resource roles. |
| **Chargeable categories** | Manage chargeability for transaction categories. |
| **Project Contract Line Details** | Review and maintain the detailed estimates and financial components for the line. |
| **Invoice schedule** | Review and manage the invoice schedule or billing milestones. |
| **Customers** | Review customer and split-billing information for the line. |
| **Related** | Open other records related to the contract line. |

#### Configure chargeable tasks

Use the **Chargeable Tasks** tab to define the billing setup for project tasks associated with the contract line. This tab is especially useful when **Included tasks** is set to **Selected project tasks only**.

Select the project tasks that belong to the contract line and define how transactions for those tasks are billed. The task selection works with the included transaction classes on the Summary tab to determine which contract line applies to project actuals and estimates.

#### Configure chargeable roles

Use the **Chargeable roles** tab to manage billing rules for resource roles on the contract line. Specify whether work performed by a role is chargeable or nonchargeable.

Role chargeability helps determine whether time transactions for a resource role contribute to billable sales. The available roles are based on the project and pricing setup associated with the contract line.

#### Configure chargeable categories

Use the **Chargeable categories** tab to manage billing rules for transaction categories, such as expense categories. Specify whether transactions in a category are chargeable or nonchargeable for the contract line.

Category chargeability is used with the project, included tasks, and included transaction classes to determine how project transactions are processed for billing.

#### Work with project contract line details

Select **Project Contract Line Details** to open the line-details experience for the selected contract line. This tab uses the full page width to present detailed estimate and billing components in one workspace.

Depending on the transaction class, a line detail can include the project task, role, transaction category, quantity, dates, cost rate, sales rate, cost amount, and sales amount.

From this tab, you can create, edit, or delete eligible line details. Select a line detail and then select **Open cost detail** to review its cost information while retaining the contract-line context.

#### Manage the invoice schedule

Use the **Invoice schedule** tab to review and manage how the contract line is invoiced. The available schedule depends on the billing method and invoice schedule type.

For a fixed-price line, the schedule can include billing milestones or progress-based billing entries. For a time and material line, invoicing is based on eligible project actuals. From this tab, you can review invoice dates, amounts, milestone or progress information, and billing status.

#### Manage contract line customers

Use the **Customers** tab to review and manage the customers that share responsibility for the contract line. Split-billing rules define the percentage of the line that is billed to each customer.

The billing percentages for the line must total 100 percent. When required, identify the rounding customer that receives any rounding difference produced during invoice calculation.

## Analysis tab

The **Analysis** tab provides contract-level insights that span all contract lines. Contract analysis focuses on actuals compared with plan, billing performance, and delivered margin.

### Review contract performance

The **Contract performance** section shows when the information was last updated, and organizes health information into three cards, each with its own health badge (**Healthy**, **At risk**, or similar status). For steps to customize the KPI card health badges, see [Customize health badges in the modern contract experience](customize-health-badge-modern-contract.md).

| Card | Health badge reflects | Fields shown |
| ------ | ----------------------- | -------------- |
| **Profitability** | Gross margin performance against the expected margin. | **Gross margin**, **Expected gross margin** |
| **Cost performance** | Actual cost against the estimated cost. | **Actual cost**, **Estimated cost**, **Cost variance** |
| **NTE utilization** | How much of the contract NTE limit has been consumed. | **NTE utilization**, **Contract NTE limit**, **Remaining NTE** |

- **Gross margin** and **Expected gross margin** show the actual and projected margin percentages for the contract.
- **Actual cost**, **Estimated cost**, and **Cost variance** compare the costs incurred against the estimate, with the variance shown in parentheses when actual cost exceeds the estimate.
- **NTE utilization** shows the percentage of the contract NTE limit that has been consumed. **Contract NTE limit** and **Remaining NTE** show the total limit and the amount still available.

Select the refresh control to recalculate the section using the latest data.

### Review contract line performance

The contract line performance chart compares:

- Actual spend
- Actual margin
- Planned budget
- Expected margin

Lines where actual spend exceeds the planned budget are candidates for further review.

### Review billing efficiency

The billing efficiency chart compares billed and unbilled amounts over time. If the billed amount remains flat while the unbilled amount grows, billing might not be keeping pace with delivery. If the values converge, billing is catching up with delivered work.

Use the time scale controls to review the chart by month or quarter and move between periods.

### Compare project line performance

The project lines performance table provides a sortable comparison of contract lines.

| Column | Description |
| -------- | ------------- |
| **Line name** | Opens the actuals pane for the line. |
| **Contract value** | The committed amount for the line. |
| **Billed amount** | The invoice-posted amount for the line. |
| **Cost incurred** | Actual costs for the line. |
| **Gross margin** | Actual margin for the line. |
| **Expected margin** | Projected margin for comparison. |
| **Project budget variance** | Compares actual cost and the approved project budget. |
| **NTE status** | Shows NTE utilization and whether the line is Within NTE, At risk, or Over NTE. |

## Details tab

The **Details** tab contains the contract setup fields and split billing rules for the contract.

### Review contract setup fields

The tab contains contract setup and administration fields, including:

- Billing or invoice address
- Payment terms
- Price list
- Originating opportunity or quote
- Notes
- Attachments

### Manage split billing rules

Split billing rules define how billing is distributed between customers at the contract or contract line level. The rules include:

- Customer
- Billing percentage
- Rounding customer

The billing percentages must total 100 percent before you can save the rules.

## Advances and retainers tab

Use the **Advances and Retainers** tab to manage customer advances and retainer schedules.

The tab shows:

- Retainer schedule entries and their statuses
- Total retainers applied
- Outstanding retainer balance
- Applied and remaining retainer amounts

From this tab, you can add invoice lines, create an invoice from retainers, or refund retainer lines when the action is available.

## Additional information

- [Header details for project contracts](../pro/sales/project-contract-settings-sales.md)
- [Project contract lines overview](../pro/sales/manage-contract-values-project-based-sales.md)
