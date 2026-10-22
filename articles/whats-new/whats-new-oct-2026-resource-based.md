---
title: What's new October 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the October 2026 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 10/22/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new October 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.172.3572.4.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.49.

## Project Operations dual-write map updates

The Project Operations October 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry | **Configure Minimum Interval for Time Entry Duration** <br><br> This new time entry configuration allows administrators to set minimum interval for time entry duration (For example, Time entries must be created in intervals of 15 mins). Time entries with durations that are not in exact multiples of this minimum interval get rounded up to the nearest, higher multiple of the interval. | [Configure minimum interval for time entry duration](../time/time-entry-configurations.md#configure-minimum-interval-for-time-entry-duration) |
| Project Planning | **Import Task - Public API support** <br><br> Public API for the Import tasks capability enables customers and partners to programmatically import tasks from one project into another. Organizations can call these APIs from custom applications, integrations, or automated workflows instead of requiring a user to initiate each import manually. | |
| Billing | **Allow to invoice future-dated transaction** <br><br> Use the Accounting date as the transaction cutoff date for project invoices, enabling eligible future-dated transactions through that date to be included. This allows billing teams to prepare invoices in advance while controlling the accounting period in which the resulting transactions are recorded. | |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Actuals | 6293038 | Async processes can bypass actual validations and cause data corruption. |
| Approvals | 6521379 | When you add related columns to the Approvals view, it breaks the rendering of hours. |
| Approvals | 6557863 | Incorrect duration display in Calendar view Time Phased Approvals (Dutch format). |
| Billing | 5989595 | Importing invoice line transactions doesn't trigger recalculation on the parent Invoice Line or Invoice. |
| Billing | 6514403 | Posted correction invoice is missing tax information. |
| Billing | 6514537 | Correction invoice can't be posted if tax is removed. |
| Billing | 6598554 | You can edit the Integration Key value in Dataverse for Contract Line Schedule, which causes duplicate records in finance and operations apps. |
| Billing | 6641322 | Invoice **Update totals** doesn't recalculate invoice line amounts in new invoicing experience. |
| Billing and Pricing | 3597409 | Currency isn't correctly defaulted for sales journal lines. |
| Pricing | 6256862 | Price List isn't stamped on Journal Line, setting price to NULL. |
| Pricing | 6542608 | Multi-currency: Import from Estimate leaves Quote Line Cost Total unconverted. |
| Pricing | 6629271 | Inactive price overrides block updating of price list start and end dates. |
| Project And Resource Management | 6701315 | Incorrect error message: Import Task with empty task list. |
| Project Estimates | 6629380 | Estimate-line updates incorrectly require a paired sales line on every update. |
| Quote | 6114169 | Price override isn't carried over when Quote is revised. |
| Resource Management | 6382335 | Stale fields on Resource Assignment after rebooking from a contract worker to employee via Schedule Board. |
| Resource Management | 6719575 | Bulk resource reconciliation repeatedly submits the full booking cancellation list. |
| Sales | 6002415 | Quote line cost amount is wrong when cost Quote Line Detail is in a different currency. |
| Sales | 6630658 | You can delete milestones only from the context of an OrderLine form. |
| Sales | 6686707 | Dual-write upgrade fails merging QuoteDetail form with zero cell ordinal. |
| Subcontracting | 6675803 | Vendor Invoice read-only validation doesn't fire for single or two-field edits. |

## Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1156136&dbType=3&qc=40dd639253c871684fa1bcc4740fa3b1ee0e59f724196d6c4e76c35ce03a5876).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
