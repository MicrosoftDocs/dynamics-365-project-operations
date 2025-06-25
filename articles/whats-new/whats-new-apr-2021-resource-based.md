---
title: What's new April 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the April 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new April 2021 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.9.0.221
- Project management and accounting in Dynamics 365 Finance environment version 10.0.17

## Features included in this release

The following features are included in this release:

- Non-stocked materials for projects. Key capabilities include:
  - Estimating and pricing non-stocked materials during the sales cycle for a project. For more information, see [Set up cost and sales rates for catalog products - lite](../pro/pricing-costing/set-up-cost-sales-rates-catalog-products.md).
  - Tracking the use of non-stocked materials during project delivery. For more information, see [Record material usage on projects and project tasks](../material/material-usage-log.md).
  - Invoicing used non-stocked material costs. For more information, see [Manage billing backlog](../proforma-invoicing/manage-billing-backlog.md).
  - For information about how to configure this feature, see [Configure non-stocked materials and pending vendor invoices](../procurement/configure-materials-nonstocked.md)
- Task based billing: Added the ability to associate project tasks with project contract lines, thereby subjecting them to the same billing method, invoice frequency, and customers as those on the contract line. This association ensures accurate invoicing, accounting, revenue estimation, and recognition to work in accordance with this setup on project tasks.
- New APIs in Dynamics 365 Dataverse allow create, update, and delete operations with **Scheduling entities**. For more information, see [Use Schedule APIs to perform operations with Scheduling entities](../project-management/schedule-api-preview.md).

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations April 2021 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration actuals (msdyn\_actuals) | 1.0.0.14 | Map modified to synchronize material project actuals. |
| Project Operations integration entity for expense estimates (msdyn\_estimateslines) | 1.0.0.2 | Added project contract line sync to finance and operations apps for task-based billing support. |
| Project Operations integration entity for hour estimates (msdyn\_resourceassignments) | 1.0.0.5 | Added project contract line sync to finance and operations apps for task-based billing support. |
| Project Operations integration table for material estimates (msdyn\_estimatelines) | 1.0.0.0 | New table map to synchronize material estimates from Dataverse to finance and operations apps. |
| Project Operations integration project vendor invoice export entity (msdyn\_projectvendorinvoices) | 1.0.0.0 | New table map to synchronize vendor invoice headers from finance and operations apps to Dataverse. |
| Project Operations integration project vendor invoice line export entity (msdyn\_projectvendorinvoicelines) | 1.0.0.0 | New table map to synchronize vendor invoice lines from finance and operations apps to Dataverse. |

You should always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and finance and operations solution version. Certain features and capabilities might not work correctly if the latest version of the map is not activated. You can see the active version of the map in the **Version** column on the **Dual-write** page. You can activate a new version of the map by selecting **Table map versions**, selecting the latest version, and then saving the selected version. If you have customized an out-of-the-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue with starting the map, follow instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

### Project Operations in Dynamics 365 Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2124532 | The **Correct Invoice** button is displayed on a proforma invoice when the retainer amount or applied retainer amount is present on the original invoice. The button is displayed only for environments with Finance version 10.0.19 or higher. |
| Billing and pricing | 2224568 | Added logic to enable customizations that involve invoking the invoice confirmation plug-in. |
| Billing and pricing | 2101098 | Improved the logic of default fields to proforma invoice: **Bill-to Address**, **Bill to Name**, and **Payment Terms** now default from the corresponding project contract customer record. |
| Billing and pricing | 2021413 | Updated the **Actual Cost** and **Sales** fields on the **Task** entity to include sales values from unbilled and billed expenses on tasks. |
| Billing and pricing | 2182110 | When copying a project contract, the contract line ID is regenerated in the destination project contract to ensure it's unique. |
| Opportunity Management | 2186741 | Added validations to ensure the **Origin** field and **Transaction Type** can't be updated on existing quote line details. |
| Opportunity Management | 2191353 | Milestones must not be created on a time and material contract line. |
| Opportunity Management | 2216956 | Fixed issues with **Update prices**. |
| Planning and Tracking | 2182979 | Project copy function improved to ensure the expense estimate lines are copied from the original project. |
| Planning and Tracking | 2184144 | Project copy function improved to ensure the resource position name is copied from the original project. |
| Planning and Tracking | 2184799 | Project copy: Tightened control to ensure the estimated start date can't be changed while copying is in progress. |
| Planning and Tracking | 2185134 | Project copy: Destination project estimated start date is set to today's date. |
| Planning and Tracking | 2196373 | Project copy: Ensure the project manager and team member records aren't duplicated in the project team. |
| Planning and Tracking | 2211833 | Project copy: Resource assignments are copied from the source project task to the destination project. |
| Planning and Tracking | 2186541 | Fixed issues in the **Estimates** grid when grouping by resource. |
| Planning and Tracking | 2166906 | The transaction category from a task must be copied to the **Resource Assignment** entity. |
| Resource Management | 2125362 | Fixed issues with creating a generic team member using an hours-based allocation method. |
| Time and Expense | 2113603 | Fixed the customization-related issue with removing attributes from the **Time Entry** page. The system now checks if the attribute exists on the page before accessing them by using a script. |
| Time and Expense | 2204377 | Copied timesheets must show automatically when you select **Copy Week** during time entry. |
| Time and Expense | 2209059 | **Status** field can be edited for Dynamics 365 Field Service time entries. |

### Project management and accounting in Dynamics 365 Finance

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Project management and accounting | [491941](https://fix.lcs.dynamics.com/Issue/Details/?bugId=491941) | Reverse estimate elimination isn't working in the **Periodic** section.  |
| Project management and accounting | [509773](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509773) | The **Accounting adjustment** feature creates an issue with ledger accounts that have **Do not allow manual entry** selected. |
| Project management and accounting | [510728](https://fix.lcs.dynamics.com/Issue/Details/?bugId=5109728) | Added business logic to process correction invoices including retainer amount or applied retainer amount. |
| Project management and accounting | [514364](https://fix.lcs.dynamics.com/Issue/Details/?bugId=514364) | WIP-sales value posting in intercompany project invoicing picks an unexpected account. |
| Project management and accounting | [521807](https://fix.lcs.dynamics.com/Issue/Details/?bugId=521807) | When working with retainers in Project Operations, changing the default project on a contract after the prepayments are invoiced causes issues with incoming deductions. |
| Project management and accounting | [527319](https://fix.lcs.dynamics.com/Issue/Details/?bugId=527319) | In Project Operations, removing a project from a contract should reset the default project of the contract, if needed. |
| Project management and accounting | [528212](https://fix.lcs.dynamics.com/Issue/Details/?bugId=528212) | In Project Operations, the wrong expense lines show in the **Add line** list on the intercompany invoice. |
| Project management and accounting | [543968](https://fix.lcs.dynamics.com/Issue/Details/?bugId=543968) | In Project Operations, the **Purchase Agreement** page isn't visible in Finance legal entities that are integrated with Project Operations. |
| Project management and accounting | [545878](https://fix.lcs.dynamics.com/Issue/Details/?bugId=545878) | Because of a Dataverse integration error, you can't convert a quote to won in Project Operations. |
| Project management and accounting | [547440](https://fix.lcs.dynamics.com/Issue/Details/?bugId=547440) | **ProjCDSProjectContractEntity** can set the funding source invoice address from a different customer.  |
| Project management and accounting | [557376](https://fix.lcs.dynamics.com/Issue/Details/?bugId=557376) | In Project Operations, no dimensions are selected when you create a posting invoice for a transaction. |
| ravel and Expense | [441256](https://fix.lcs.dynamics.com/Issue/Details/?bugId=441256) | The cash advance balance isn't updated for an expense report if it's approved and posted line by line. |
| Travel and Expense | [482041](https://fix.lcs.dynamics.com/Issue/Details/?bugId=482041) | Taxes for itemized intercompany expense reports aren't calculated correctly. |
| Travel and Expense | [483469](https://fix.lcs.dynamics.com/Issue/Details/?bugId=483469) | Additional fields related to projects are displayed on the reimagined **Intercompany expense reports** page. |
| Travel and Expense | [486592](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486592) | An incorrect error message occurs on the header receipts of expense reports. |
| Travel and Expense | [487971](https://fix.lcs.dynamics.com/Issue/Details/?bugId=487971) | An expense report is incorrectly posted in an intercompany scenario if the sales tax is posted to the destination legal entity. |
| Travel and Expense | [505696](https://fix.lcs.dynamics.com/Issue/Details/?bugId=505696) | Report submission dates aren't printed on approved expense reports. |
| Travel and Expense | [508726](https://fix.lcs.dynamics.com/Issue/Details/?bugId=508726) | The **Date Approved** and **Date Rejected** fields aren't populated after an expense is approved. |
| Travel and Expense | [509913](https://fix.lcs.dynamics.com/Issue/Details/?bugId=509913) | A travel requisition created for one worker can be used for another worker's expense report. |
| Travel and Expense | [518186](https://fix.lcs.dynamics.com/Issue/Details/?bugId=518186) | Expense categories are locked when adding a new expense line. |
| Travel and Expense | [520914](https://fix.lcs.dynamics.com/Issue/Details/?bugId=520914) | Itemizing an already split expense report lines results in an incomplete posting of the Accounts Payable\General Ledger voucher and breaks the Accounting Source Explorer because **TRVEXPTRANS.SOURCEDOCUMENTLINE** is duplicated. |
| Travel and Expense | [521943](https://fix.lcs.dynamics.com/Issue/Details/?bugId=521943) | The travel requisition policy isn't working as expected. |
| Travel and Expense | [522567](https://fix.lcs.dynamics.com/Issue/Details/?bugId=522567) | The vendor account name isn't showing on posted project transactions for expense reports. |
| Travel and Expense | [525106](https://fix.lcs.dynamics.com/Issue/Details/?bugId=525106) | In Project Operations, you can't approve time with a task for an intercompany project. |
| Travel and Expense | [526336](https://fix.lcs.dynamics.com/Issue/Details/?bugId=526336) | The cash advance return category isn't updating cash advance balances when posted. |
| Travel and Expense | [527218](https://fix.lcs.dynamics.com/Issue/Details/?bugId=527218) | The sales price is calculated incorrectly on expense reports that were created in a foreign currency using imported credit card transactions and are associated with a project. |
| Travel and Expense | [542927](https://fix.lcs.dynamics.com/Issue/Details/?bugId=542927) | Rolled back the **TrvRequisitionLine** data entity and the associated unique index. |
| Travel and Expense | [543239](https://fix.lcs.dynamics.com/Issue/Details/?bugId=543239) | Added instrumentation to the **SOURCEDOCUMENTLINE** generation. |
| Travel and Expense | [544323](https://fix.lcs.dynamics.com/Issue/Details/?bugId=544323) | The wrong subledger journal is shown in an intercompany scenario if sales tax is posted to the destination legal entity. |
| Travel and Expense | [546877](https://fix.lcs.dynamics.com/Issue/Details/?bugId=546877) | In Project Operations, expense estimates aren't deleted from Finance when they are deleted from Dataverse. |
| Travel and Expense | [550575](https://fix.lcs.dynamics.com/Issue/Details/?bugId=550575) | When an expense category is a non-project category, the financial dimensions selected on the **Expense** page aren't copied to the expense report. |
