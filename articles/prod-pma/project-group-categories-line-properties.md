---
title: How project groups, categories, and line properties determine project posting
description: This article describes project posting setup and the impact on posting and reporting from groups, categories, and line properties
author: ryansandness
ms.author: ryansandness
ms.reviewer: johnmichalak
ms.topic: how-to
ms.date: 12/12/2025
ms.custom:
  - bap-template
---
# How the project group, categories, and line property determines project postings

_**Applies To:** Project Operations for manufacturing-based scenarios_

Project Operations offers robust capabilities for capturing cost and revenue associated with projects. Project postings are the financial results driven from the business processes such as posting a packing slip or processing revenue recognition. These results are driven by a combination of:

- The project transaction type (hour, expense, item, fee, and on-account)
- Project categories and their category group
- Project group configuration
- Line properties
- Configuration and set up

This article explains how these settings work together to determine:

Which ledger accounts are used
Whether postings impact the profit and loss (P&L) or balance sheet (WIP) on your financials
When revenue is accrued ahead of invoicing
Whether costs are capitalized or expensed

## Project transaction types

Five predefined transactions types are supported in Project management and accounting:

- Hour – Transactions are linked to the financial compensation of project workers, such as consulting, installation, or design.

- Expense – Transactions are associated with a project, unless the transactions are related to items or costs. Examples include travel expenses or vendor services.

- Item – Transactions are linked to items that are purchased for resale, and to items that are consumed in a project, such as when a customer purchases a new computer for the project through the company.

- Fee – Fixed revenues are associated with a Time and material project, such as a bonus for the early delivery of a project blueprint plan and budget.

- On-account - Transactions that represent prepayments for either a Fixed-price or Time and material project or scheduled payments for a Fixed-price projects.

## Project Categories and groups

You can categorize revenue and expenses on projects to control posting to the general ledger, and for detailed reporting and analysis. By categorizing expenses and revenues separately from the general ledger, project managers can get more details about project performance.

Category groups are the first thing to setup when categorizing a set of similar transactions of a specific type. Category groups let you share properties, primarily posting profiles, between related categories. At least one category group must be created for each transaction type, and each project category must be assigned a category group. Because project categories are assigned to a single group, they're associated with the same transaction type as the category group. You can set up category groups by going to Project management and accounting > Setup > Categories > Category groups.

Project categories are the basic grouping for project transactions. Individual project categories can have unique cost and revenue accounts and be used to differentiate between travel expenses related to hotels, and travel expenses related to mileage. When you enter a project category on a transaction line, the category selection is limited to the categories that are set up and linked to this transaction type. For example, when an expense transaction is entered, only expense categories are available. You can set up categories by going to Project management and accounting > Setup > Categories > Project categories.

Shared categories are a parent grouping of project categories that can be shared across applications and modules. Microsoft Dynamics 365 uses the shared categories concept to categorize expenses in different applications, such as Microsoft Dynamics 365 Finance, Microsoft Dynamics 365 Supply Chain, and Project Operations. A shared category must exist before a project category can be created in any consuming legal entity. You can review and adjust the shared categories by going to Project management and accounting > Setup > Categories > Shared Categories.

## New functionality to allow categories on on-account type transactions

With the 10.0.47 release, there's a new feature that lets you create a category and group for on-account type transactions. Within Feature management, the Enable project categories for on-account transactions feature is now available. New functionality enabled by this feature includes:

- Project management and accounting parameters have a new default setting to default the category for on-account transactions. This default applies to both retainers and milestone transactions.
- The Category groups form now allows you to configure groups of type on-account.
- The Project categories form now allows you to configure a category of type on-account.
- Category is added as an optional field. Existing on-account transactions continue to work without a category configured. New on-account transactions work with or without a category defined. Posting continues to be based on the setup of Ledger posting setup for the Invoiced revenue - on-account posting type.
- The Ledger posting setup form was enhanced to allow for configuration of a specific main account for a specific category relation. This enhancement allows users to set up a different revenue account for different categories.
- The On-account form allows for editing of the category, and the Project invoice proposal form before posting.

## Project Groups

Your project could be an internal project tracking costs only, or it could be a revenue generating project. The different project types are discussed more in [Create Projects](/dynamics365/project-operations/prod-pma/overview-project-management-accounting). Project groups provide the ability to determine many of the fundamental accounting rules of how the project financials should be generated for a given project type. For hour, expense, item, and on-account transactions, you can choose to post transactions to either Profit and loss or Balance accounts. In certain cases, you can also choose not to post hour transactions.

Every project must belong to a project group. Therefore, you must set up at least one project group when you set up Project management and accounting.

A project must be assigned to a project group that was created for that type of project. If you move a project from one project group to another, and the new project group was created for a different project type, the project is automatically changed to the new type.

After you set up a project group in the Project groups form and select its project type, you can specify several default settings for it. These settings include transaction line properties, on-account invoice posting, journalizing, and cost and revenue accounts.

- Invoicing – Determine whether on-account invoices for Time and material and Fixed-price projects are posted to revenue accounts or work-in-process (WIP) accounts.

- Journalizing – Indicate whether hour costs, expense costs, and item costs should be posted to Profit and loss accounts or Balance accounts, or not posted. When transactions are posted in the respective transaction, the system performs a check to ensure that a ledger account is available, and that the account is the appropriate type.

- Cost accounts and Revenue accounts – Specify whether a specific ledger account applies in every situation and to every project in this group. If more flexibility is required, you can set up ledger posting at the category level or project level.

After a project is assigned to a project group, the options that are defined for ledger updates in the project groups can't be changed.

## Line properties

Use the line properties to set posting behavior about hour, fee, expense, and item transaction lines. When you create transactions for projects, the default line properties are automatically added to the lines in journals, invoices, and other postings. By setting up default line properties, you can minimize repetitive tasks when you work with projects.

The key settings in line properties include the setting for if chargeable or not, whether for WIP posting to accrue revenue or not, and lastly the option to capitalize cost or not.

The purpose of the line property depends on the project type:

- Fixed-price and investment projects – The line property affects only whether the cost amount is capitalized as a fixed asset.

- Time and material projects – The line property controls whether transactions are chargeable or nonchargeable, whether the sales amount is accruable or nonaccruable, and whether the cost amount is capitalized as a fixed asset.

The **Capitalize cost** setting on line properties plays a crucial role in how project-related costs are treated in accounting, especially in terms of asset capitalization vs. expense recognition.

Typical line property examples:

Chargeable – Billable, accrue revenue, capitalize cost
Non‑chargeable – Not billable, no revenue, direct P&L
Internal – No revenue, but costs can be capitalized (for example, investment projects)

| Group/Rule | Line property Capitalization | Resulting Posting layer |
|---|---|---|
| Fixed price – Balance | Yes | Balance sheet |
| Fixed price – Balance | No | P&L |
| Fixed price – P/L | Yes | P&L |
| Fixed price – P/L | No | P&L |
| Time and material – Balance | Yes | Balance sheet |
| Time and material – Balance | No | P&L |
| Time and material – P/L | Yes | P&L |
| Time and material – P/L | No | P&L |
| Investment | Yes | Balance sheet |
| Investment | No  | P&L |

## Revenue Recognition Elimination

For fixed-price and investment type projects, whether or not the project is eliminated can determine posting behavior. If the project is a balance sheet type project, but the project has already been eliminated then any new postings to the project will post directly to profit and loss.

## How project groups, categories, and line properties work together

When you post a project transaction (for example, an hour journal or item requirement), the posting engine works roughly as follows:

1. Determine transaction type and project type
   - Example: Hour transaction on a Time and material project.

2. Determine whether cost goes to profit and loss or balance sheet
   - Uses project group journalizing and line property capitalization to decide P&L expense account vs WIP cost account.

3. Apply line property rules
   - Chargeable = invoicing behavior
   - Accrue revenue = use accrued revenue accounts which will generate an additional accounting record on transaction posting.
   - Capitalize cost = post to WIP accounts to override project group

4. Select main accounts. Evaluate posting rules using ledger posting setup using:
   - Project / project group
   - Category / category group
   - Funding source (when used)
   - Apply All / Group / Table precedence; category‑specific settings override group‑level.

5. Create ledger entries
   - For each posting type (Cost, WIP cost, Revenue, Accrued revenue, Invoiced revenue, etc.), debit and credit accounts are derived from the referenced configuration.
