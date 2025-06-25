---
title: What's new June 2025 - Project Operations Lite deployment
description: This article provides information about quality updates that are available in the June 2025 release of Microsoft Dynamics 365 Project Operations Lite deployment.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 06/25/2025
ms.reviewer: johnmichalak
---

# What's new June 2025 - Project Operations Lite deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.142.0.166.

## Features included in this release

There are no new features released in the June 2025 version of Project Operations lite deployment.

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing| 4655493| Invoice can't be confirmed when the total amount is negative and a new retainer is raised on the same invoice. |
|Billing and Pricing| 4872141| Journal line not posted when approval is canceled, leaving the created actuals unchanged without the adjustment status. |
|Billing and Pricing| 4995210| Invoice Line without name ignores chargeability when calculating amount. |
|Billing and Pricing| 5024102| Trying to mark the contract line as "Ready to invoice" in billing hub results in "Billing status can't be updated on a contract line that isn't product-based." |
|Billing and Pricing| 5054756|	Origin field on sales estimate line should be allowed to update from null. |
|Billing and Pricing| 5079606| Script error when selecting Project Task on a time entry correction journal. |
|Billing and Pricing| 5124144| Can't Delete Recalled Time Entries Associated to Revised Invoices. |
|Project Budgeting| 4829338| Unable to see dropdown values in Transaction Category field. |
|Sales| 5005220| Create Order throws "The contract line can't be updated directly." |
|Sales| 4926105| Invoice schedule type not validated on quote line update. |
|Subcontracting| 4450523| Task doesn't get linked to contract line during billing setup. |
|Time Entry| 4871947| Time entry issues for associated view are now handled by updating fields that appear on this view. |
|Time Entry| 5089432| Modern Grid - Unable to create Time entries inline when working on the grid other than English. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
