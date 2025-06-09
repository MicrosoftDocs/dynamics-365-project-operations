---
title: What's new or changed in Project Operations, November 2023 for stocked/production-based scenarios
description: This article provides information about the quality updates that are available in the November 2023 release of Microsoft Dynamics 365 Project Operations for stocked/production-based scenarios.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: tulsijhaveri
---

# What's new or changed in Project Operations, November 2023 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production-based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.37

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Financials | **Enable recalculation of funding limits** A new feature is available by enabling the referenced parameter under Project Management and Accounting in the invoicing tab. This feature allows tracking history of funding limit spent amounts and the ability to recalculate funding limit spent amounts in the case of an issue with a customization or product bug. | [Project contracts](../../prod-pma/project-contracts.md) |
| Procurement | **Enable project purchase order product receipt cancellation with linked item requirements** This feature enables users to cancel purchase order (PO) product receipts with linked item requirements. Previously many scenarios were blocked with the error message "cannot cancel the product receipt \*\*\* as it has linked item requirements." This feature requires the "Enable packing slip cancellation for item requirements" feature to be enabled as a prerequisite and also enables the new posting logic in that feature to apply to item requirements linked to purchase orders. | [Receive items on purchase order from item requirement](../../prod-pma/tasks/receive-items-purchase-order-item-requirement.md) |

## Quality updates

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=838613).
