---
title: What's new September 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the September 2026 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 09/21/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new September 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.171.3551.6.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.49.

## Project Operations dual-write map updates

The following table shows the dual-write maps that are modified or added in the Project Operations March 2026 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project subscription billing schedule header (msdyn_subscriptions) | 1.0.0.0 | Added as a part of the Subscription Billing feature |
| Project subscription billing schedule lines (msdyn_subscriptionlines) | 1.0.0.0 | Added as a part of the Subscription Billing feature |
| Project subscription billing detail lines (msdyn_subscriptionbillingdetails) | 1.0.0.0 | Added as a part of the Subscription Billing feature |
| Project contract lines (salesorderdetails) | 1.0.0.3 | Latest version updated |
| Project invoice proposals V2 (invoices) | 1.0.0.5 | Latest version updated |

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry | **Use Outlook Meetings as a time entry source** <br><br> is a new configuration that enables team members to view Outlook meetings on the Time Entry Calendar interface and then use them to create time entries as well. | [Use Outlook as a time entry source](..//time/time-entry-configurations.md#use-outlook-meetings-as-a-time-entry-source) |
| Resource Management | **Configure Default Booking Methods** <br><br> Project Operations allows administrators to define default booking methods while using the Schedule Assistant or Schedule Board directly for booking resources. These defaults help standardize resourcing behavior across projects and reduce manual selection by project managers and resource managers. | [Configure booking methods in Project Operations](../resource-management/booking-allocation-methods.md#configure-default-booking-methods) |
| Procurement | **Enable purchase orders and item requirement for stocked items in Project Operations integrated with ERP** <br><br> This feature helps reduce manual effort and procurement delays by automatically generating item requirements from purchase orders based on the configuration of the Create Item Requirement and Item Consumption parameters. When this feature is enabled, updating the packing slip for an item requirement in finance and operations automatically triggers the creation of a corresponding Material Usage transaction on the project in Project Operations through dual-write synchronization. This ensures that material consumption is accurately reflected in Project Operations without requiring manual intervention. | |
| Billing | **Subscription billing in Project Operations Integrated with ERP** <br><br> Subscription billing brings recurring, schedule-driven billing into the Project Operations contract and invoicing experience. You set up a subscription on a project contract line, Dynamics 365 Finance generates the billing schedule and the billing details, and those details flow back into Project Operations where they're invoiced through the same proforma invoicing process you already use for time and material and fixed-price work. | |
| Billing | **Assign transaction categories to on-account transactions** <br><br> On-account transactions, retainers, advances, milestones, and progress-based billing, can now carry a Transaction category. The category selected in Project Operations determines the project category that Finance uses when the transaction posts, so revenue for different types of on-account billing can be directed to different main accounts. | |
| Investment Projects | **Enable Handling of Multiple Eliminations in Investment Projects** <br><br> You can now configure and process multiple eliminations for a single investment project, providing greater flexibility in managing investment transactions and supporting more complex project accounting scenarios. This feature removes the existing limitation of a single elimination per investment project. Finance and project accountants can now post multiple elimination transactions against the same investment project, enabling support for staged capitalization, cost overruns, and partial expense recognition scenarios. | [Investment Projects](..//prod-pma/multiple-eliminations-investment-project.md) |
| Revenue Recognition | **Enable Project Budget management feature in Project Operations integrated with ERP** <br><br> The Project Budget Management experience for non-stocked and resource-based projects has been enhanced to provide greater flexibility during revenue recognition. In addition to estimate forecast models, users can now select a budget forecast model when performing estimations for revenue recognition. | [Revenue Recognition using project budget management](..//revenue-recognition/rev-rec-completed-contract-method.md) |
| Project Management | **Manage task grid column permissions** <br><br> Control column-level edit access in the task grid by configuring permissions at the organization, user, and project team member levels. Create permission templates and assign them across these levels to streamline administration and ensure consistent access management. | |
| Project Management | **Default task grid view** <br><br> You can now create and apply column configurations on the task grid which helps you to get a consistent view across the projects. Users still have the option to alter the view per project basis. Apply these templates at the organization level and per project level. You can also enforce the view settings to ensure users aren't allowed to alter the task grid view beyond allowed columns. | |
| Project Management | **Multiple Baselines** <br><br> Project Operations now supports 11 baselines, matching the Project Desktop experience. Capture multiple snapshots throughout the project lifecycle and compare them to understand how your project evolved over time. | |
| Project Management | **Task level calendars** <br><br> Task-level calendar support is now available in Project Operations. Assign different calendars to tasks, and the scheduling engine automatically uses them when calculating schedules, improving scheduling accuracy and reducing the need for off-system workarounds. | |
| Project Management | **Lookup and Currency Support for Custom Columns** <br><br> Add lookup and currency columns to the task grid to display related records and financial information directly within the grid, reducing the need for task form customizations. | |
| Journals | **New correction journal experience** <br><br> The new correction journals experience in Project Operations makes it easier to correct approved time, expense, and material transactions. You can combine different transaction types in a single journal, add entries to an existing draft, and apply different corrections to selected groups of entries through an editing side pane. Expanded correction options include quantities, billing type, and cost and sales prices, alongside project, task, resource, and transaction-specific fields. You can preview reversal and replacement journal lines before confirming, while entry-level correction status helps distinguish modified entries from unchanged entries. The new experience is initially optional, so organizations can continue using the existing correction journals experience until they enable it. | |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Actuals | 6293038 | Asynchronous processes can circumvent validations on actuals and lead to data corruption. |
| Approvals | 5927451 | Journal lines can be deleted in most scenarios. |
| Billing | 5989595 | Importing Invoice line transactions doesn't trigger recalculation on parent Invoice. |
| Billing | 6514403 | Posted correction invoice is missing tax information. |
| Billing | 6514537 | Correction invoice can't be posted if the tax is removed. |
| Billing | 6524553 | Retainers show up incorrectly on Billing Hub. |
| Billing | 6641322 | Invoice "Update totals" doesn't recalculate invoice line amounts - totals remain stale in new invoicing experience. |
| Pricing | 6247963 | Wrong price list picked up on save of Material Usage Log. |
| Pricing | 6256862 | Price List isn't stamped on Journal Line, price set to NULL. |
| Project And Resource Management | 6567653 | Inconsistent default values between new project and existing project when using Copy Project. |
| Resource Management | 6382335 | Stale SubcontractLine, WorkerType, and CostType on Resource Assignment after rebooking from contract worker to employee via Schedule Board. |

## Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1156136&dbType=3&qc=40dd639253c871684fa1bcc4740fa3b1ee0e59f724196d6c4e76c35ce03a5876).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
