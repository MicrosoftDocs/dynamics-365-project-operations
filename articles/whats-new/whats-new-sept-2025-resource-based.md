---
title: What's new September 2025 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the September 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 09/22/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new September 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.145.0.1040.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.45.

## Project Operations dual-write map updates

No updates for Project Operations dual-write maps in this release. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. Learn more in [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Delegation (Production Ready Preview)** <br><br> This preview feature lets team members add another user for a date range as a delegate who can view, edit, and submit time entries on their behalf.| [Time Entry Delegation](../../time/time-entry-delegation.md) |
| Proforma Invoicing |**Improve Invoice Usability with Modern Invoicing** <br><br> The modern invoicing form provides a single view of the contract, contract lines, and invoicable transactions. It adds enhancements that streamline invoice management, editing, and validation, reducing clicks and improving clarity.| |
| Actuals | **Time Zone Independent Accounting Date** <br><br> The Accounting Date field in the JournalLine, Actuals, and InvoiceLineDetails entities stores values in a time zone dependent way, which can cause inconsistencies when viewing or processing dates outside the user's local time zone. The new field `TZAAccountingDate` stores the accounting date in a time zone independent way. | [Time Zone Independent Behavior](/power-apps/maker/data-platform/behavior-format-date-time-field#behavior) |
| Revenue Recognition |**Revenue recognition based on standalone selling price** <br><br> This feature lets you track the standalone selling price for each contract line item. The revenue allocation process distributes revenue proportionally based on the ratio of each line item's standalone selling price to the total contract standalone selling price.| [Enable revenue recognition based on standalone selling price](../revenue-recognition/revenue-recognition-standalone-selling-price.md) |
| Sales |**Enable line discounts and additional fee for project operations integrated with ERP based scenarios** <br><br> This feature lets you apply discounts and fees to time and material contract lines. Integration journals and project invoices include the discounts and fees in applicable transactions.| [Manage discounts and fees overview](../pricing-costing/manage-discount-fee-calculations.md) |
| Performance |**Performance improvements across processes** <br><br> This feature lets the system process these long-running actions asynchronously: close a quote as won, confirm a contract, create, confirm, or revise invoices, copy a price list, and update prices on a project. If the system detects that a process is long running, the user sees a banner and an in-app notification when the process finishes.| |
| Subcontracting |**Enable Subcontracting UX enhancements for smoother navigation and insights** <br><br> This feature is behind the feature flag "Enable new subcontracting UX enhancements for improved insights and smoother navigation." When enabled, it delivers a more organized main form, enhanced subcontracting insights, and improved resource handling for smoother workflows, streamlining navigation and boosting visibility into subcontracting operations.| |
| Project Budget Management |**Column based time phasing of Project Budgets instead of row based (Private Preview)** <br><br> This feature adds a new column-based time phasing view for Project Budgets, complementing the existing row-based layout. A dedicated tab shows budget data in a column format, offering a clearer time-based breakdown. It's available as a limited preview, and other enhancements are planned for the upcoming release wave. To enable the feature in preprod, open a support ticket with Microsoft.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing|	5530102|	Correction journal preview fails if one or more time entries can no longer be corrected|
|Pricing|	4997620|	Can't delete transaction category as a pricing dimension|
|Pricing|	5206990|	Product bundles cause errors with the **Copy Price List** command|
|Pricing|	5210608|	`InvalidPluginExecutionException`: A dimension with this applicability and priority already exists|
|Pricing|	5516935|	Material usage log: Unit cost for work order products initializes incorrectly|
|Project and resource management|	5278591|	Project import shows duplicate fields|
|Project Estimates|	5129793|	Imported contract line detail billing type uses the estimate line value instead of the contract line task setting|
|Project Operations Time Management|	4427926|	Time entry status shows **Submitted** when it should show **Draft**|
|Project planning and tracking|	4605239|	Can't access task record from the **Team** tab|
|Project Planning And Tracking|	5223364|	Creating a team member with more than one order line resource category causes an error|
|Project Planning And Tracking|	5572782|	Copy project button isn't disabled for externally scheduled projects when the new experience isn't enabled|
|Sales|	5362696|	PBB - Default currency is set to USD instead of contract currency|
|Sales|	5365268|	Project contract customer and contract line customer currency doesn't default to the contract currency|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1046049&dbType=3&qc=f7aa322e910d462ac082be99f72719f0d233f8a7a6973b89b8deb77f5d78fe98).
