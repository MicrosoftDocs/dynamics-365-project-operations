---
title: What's new September 2025 - Project Operations Core
description: Learn about quality updates that are available in the September release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 09/22/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new September 2025 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.145.0.1040.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Delegation (Production Ready Preview)** <br><br> This feature lets a team member assign one delegate for a date range to view, edit, and submit time entries for them.| [Time Entry Delegation](../../time/time-entry-delegation.md) |
| Proforma Invoicing |**Improve Invoice Usability with Modern Invoicing** <br><br> The modern invoicing form shows contract details, contract lines, and invoiceable transactions in one view. Usability improvements streamline managing, editing, and validating invoices, reducing clicks, and improving clarity.|  |
| Actuals | **Time Zone Independent Accounting Date** <br><br> The **Accounting Date** field in the **JournalLine**, **Actuals**, and **InvoiceLineDetails** entities is stored in a time zone-dependent way, which can create inconsistencies outside the user's local time zone. The new **TZAAccountingDate** field stores the accounting date in a time zone-independent way. | [Time Zone Independent Behavior](/power-apps/maker/data-platform/behavior-format-date-time-field#behavior) |
| Performance |**Performance improvements across processes** <br><br> This feature enables asynchronous processing of these long-running processes: close a quote as won, confirm a contract, create, confirm, or revise invoices, copy a price list, and update project prices. If a process runs long, the user sees a banner notification and later an in-app notification when it completes.||
| Subcontracting |**Enable Subcontracting UX enhancements for smoother navigation and insights** <br><br> The feature flag **Enable new subcontracting UX enhancements for improved insights and smoother navigation** lets you turn on these improvements: a more organized main form, enhanced subcontracting insights, and improved resource handling for smoother workflows. These changes streamline navigation and improve visibility into subcontracting operations.| |
| Project Budget Management |**Column based time phasing of Project Budgets instead of row based (Private Preview)** <br><br> This feature introduces a column-based time phasing view for project budgets, complementing the existing row-based layout. A dedicated tab shows budget data in a column format for a clearer time-based breakdown. It's available as a limited preview, and more enhancements are planned for the upcoming release wave. To enable the feature in preprod, open a support ticket with Microsoft.| |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference no.** | **Quality update** |
| --- | --- | --- |
|Billing|	5530102|	Correction journal preview fails if one or more time entries can't be corrected.|
|Pricing|	4997620|	Can't delete transaction category as a pricing dimension.|
|Pricing|	5206990|	Product bundles cause errors when using **Copy Price List**.|
|Pricing|	5516935|	Material usage log: Unit cost for work order products initializes incorrectly.|
|Project and resource management|	5278591|	Import project shows duplicate fields.|
|Project estimates|	5129793|	Imported contract line detail billing type comes from estimate line instead of contract line task setting.|
|Project operations time management|	4427926|	TimeEntry status shows Submitted when it should be Draft.|
|Project planning and tracking|	4605239|	Can't access task record through the **Team** tab.|
|Project planning and tracking|	5223364|	Error when creating a team member with more than one order line resource category.|
|Project planning and tracking|	5572782|	Disable the **Copy project** button for externally scheduled projects when the new experience isn't enabled.|
|Sales|	5362696|	PBB - Default currency is set to USD instead of contract currency.|
|Sales|	5365268|	Project contract customer and contract line customer currency should default from the contract currency.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
