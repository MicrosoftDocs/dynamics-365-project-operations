---
title: What's new 2024 wave 2 early access - Project Operations lite deployment
description: This article provides information about the features available in the 2024 Wave 2 early access release of Project Operations lite deployment.
author: mohitmenon
ms.custom:
  - evergreen
ms.date: 08/13/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new 2024 wave 2 early access - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.110.0.10

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Project Calendar Control** <br><br> Allows users to directly edit a project's calendar on the project form. | [Define and edit project calendars](../../project-management/define-project-calendars.md)|
| Proforma Invoicing |**Improved project invoicing usability and performance** <br><br> The Billing hub experience aims to provide a consolidated view of contracts, contract lines, related actuals, and key invoicing insights. This helps accountants and billing users create proforma invoices efficiently. Users can complete invoice creation from a single unified view, eliminating the need to navigate between forms or views to validate data, thus leading to faster processing of invoices.| [Billing hub](../../proforma-invoicing/billing-hub.md) |
| Project Invoicing |**Ability to select and revise specific transactions in an invoice.** <br><br> This feature improves usability and performance of the invoice correction process. This is done by enabling users to select a subset of the transactions for correction, without needing to revise the entire invoice. This leads to efficient and shorter invoicing cycles.| [Revise project invoices](../../proforma-invoicing/revise-proforma-invoice.md) |

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Pricing |**Date effective role price override can be easily tracked in price list** <br><br> Previously, users had to expand each role in the price lists view to check for date-effective price overrides. With this new feature, if a role has one or more date-effective price overrides, the total number of overrides will be displayed in an additional column. A positive number in the 'Overrides' column indicates that there is a price override for that role.|  |
| Sales |**Price-override from Quote line details** <br><br> This feature which was previously behind a separate feature flag, will now be available by default. Users can create a role price override directly from quote line details. | |
