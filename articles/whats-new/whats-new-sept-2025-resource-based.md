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

- Project Operations in a Microsoft Dataverse environment version 4.145.0.76.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.45.

## Project Operations Dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Delegation (Production Ready Preview)** <br><br> This preview feature allows team members to add one other user (for a date range) as their delegate to view, edit and submit time entries on their behalf| |
| Revenue Recognition |**Revenue recognition based on standalone selling price** <br><br> This feature enables you to track the Standalone selling price for each contract line item. It's utilized in the revenue allocation process, where revenue is distributed proportionally based on the ratio of each line item's Standalone selling price to the Total contract standalone selling price| [Enable revenue recognition based on standalone selling price](../revenue-recognition/revenue-recognition-standalone-selling-price.md) |
| Sales |**Enable line discounts and additional fee for project operations integrated with ERP based scenarios** <br><br> This feature allows us to apply discounts and fee to the time & material-based contract lines. Integration journals and project invoices generates financials considering the discount and fee to the applicable transactions| [Manage discounts and fees overview](../pricing-costing/manage-discount-fee-calculations.d) |
| Performance |**Performance improvements across processes** <br><br> This feature enables asynchronous processing of the following long running processes: Close a quote as won, confirm a contract, create/confirm/revise invoices, copy price list, update prices on a project. If an initiated process is determined to be long-running, the user sees a banner notification and will receive an in-app notification once the process is completed.| |
| Sub-contracting |**Enable Subcontracting UX enhancements for smoother navigation and insights** <br><br> This feature is behind a feature flag "Enable new subcontracting UX enhancements for improved insights and smoother navigation". When enabled, this feature delivers: A more organized main form, Enhanced subcontracting insights, Improved resource handling for smoother workflows designed to streamline navigation and boost visibility into subcontracting operations.| |
| Project Budget Management |**Column based time phasing of Project Budgets instead of row based (Private Preview)** <br><br> This feature introduces a new column-based time phasing view for Project Budgets, complementing the existing row-based layout. A dedicated tab will be added to display budget data in a columnar format, offering a clearer and more structured time-based breakdown. Available as a limited preview, with additional enhancements planned for the upcoming release wave. To enable the feature in pre-prod, please raise a support ticket with Microsoft.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing|	5530102|	Correction journal preview fails if one or more time entries can no longer be corrected|
|Pricing|	4997620|	Unable to delete Transaction Category as pricing dimension|
|Pricing|	5206990|	Product bundles cause errors with Copy Price List|
|Pricing|	5210608|	InvalidPluginExecutionException: A dimension with this applicability and priority already exists|
|Pricing|	5516935|	Material usage log: Unit Cost for work order products are incorrectly initialized|
|Project And Resource Management|	5278591|	Import project shows duplicate fields|
|Project Estimates|	5129793|	Imported Contract Line Detail's billing type is carried from Estimate line, instead of Contract line task setting|
|Project Operations Time Management|	4427926|	TimeEntry status shows submitted while it should be draft|
|Project Planning And Tracking|	4605239|	Unable to access task record through "Team" tab|
|Project Planning And Tracking|	5223364|	Error when creating a team member that has more than one order line resource category associated|
|Project Planning And Tracking|	5572782|	Disable the copy project button for externally scheduled project when new experience is not enabled|
|Sales|	5362696|	PBB - Default Currency is set to USD Instead of Contract Currency|
|Sales|	5365268|	Project Contract Customer and Contract Line Customer currency should default from the Contract Currency|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1046049&dbType=3&qc=f7aa322e910d462ac082be99f72719f0d233f8a7a6973b89b8deb77f5d78fe98).
