---
title: What's new October 2026 - Project Operations Core
description: Learn about quality updates that are available in the October 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 10/22/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new October 2026 - Project Operations Core

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.172.3572.4.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry | **Configure Minimum Interval for Time Entry Duration** <br><br> This new time entry configuration allows administrators to set minimum interval for time entry duration (For example, Time entries must be created in intervals of 15 mins). Time entries with durations that are not in exact multiples of this minimum interval get rounded up to the nearest, higher multiple of the interval. | [Configure minimum interval for time entry duration](../../time/time-entry-configurations.md#configure-minimum-interval-for-time-entry-duration) |
| Project Planning | **Import Task - Public API support** <br><br> Public API for the Import tasks capability enables customers and partners to programmatically import tasks from one project into another. Organizations can call these APIs from custom applications, integrations, or automated workflows instead of requiring a user to initiate each import manually. | |
| Billing | **Allow to invoice future-dated transaction** <br><br> Use the Accounting date as the transaction cutoff date for project invoices, enabling eligible future-dated transactions through that date to be included. This change allows billing teams to prepare invoices in advance while controlling the accounting period in which the resulting transactions are recorded. | |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Actuals | 6293038 | Async processes can circumvent actual validations leading to data corruption. |
| Approvals | 6521379 | When you add related columns to the Approvals view, it breaks the rendering of hours. |
| Approvals | 6557863 | Incorrect duration display in Calendar view Time Phased Approvals (Dutch Format). |
| Billing | 5989595 | Importing invoice line transactions doesn't trigger recalculation on parent Invoice Line or Invoice. |
| Billing | 6514403 | Posted correction invoice missing tax information. |
| Billing | 6514537 | Correction invoice can't be posted if tax is removed. |
| Billing | 6641322 | Invoice **Update totals** doesn't recalculate invoice line amounts in new invoicing experience. |
| Billing and Pricing | 3597409 | Currency isn't correctly defaulted for sales journal lines. |
| Pricing | 6256862 | Price List isn't stamped on Journal Line, setting price to NULL. |
| Pricing | 6542608 | Multi-currency: Import from Estimate leaves Quote Line Cost Total unconverted. |
| Pricing | 6629271 | Inactive price overrides block updating of price list start and end dates. |
| Project And Resource Management | 6701315 | Incorrect error message: Import Task with Empty Task List. |
| Project Estimates | 6629380 | Estimate-line updates incorrectly require a paired sales line on every update. |
| Quote | 6114169 | Price override isn't carried over when Quote is revised. |
| Resource Management | 6382335 | Stale fields on Resource Assignment after re-booking from a contract worker to employee via Schedule Board. |
| Resource Management | 6719575 | Bulk resource reconciliation repeatedly submits the full booking cancellation list. |
| Sales | 6002415 | Quote line cost amount is wrong when cost Quote Line Detail is in a different currency. |
| Sales | 6630658 | You can delete milestones only from the context of an OrderLine form. |
| Subcontracting | 6675803 | Vendor Invoice read-only validation doesn't fire for single or two-field edits. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
