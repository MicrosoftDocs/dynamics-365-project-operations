---
title: What's new September 2025 - Project Operations Core
description: This article provides information about quality updates that are available in the September release of Microsoft Dynamics 365 Project Operations Core.
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

- Project Operations in a Microsoft Dataverse environment version 4.145.0.76.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Delegation (Production Ready Preview)** <br><br> This preview feature allows team members to add one other user (for a date range) as a delegate that gets to view, edit and submit time entries on their behalf.| |
| Proforma Invoicing |**Improve Invoice Usability with Modern Invoicing** <br><br> The modern invoicing form builds a consolidated view of contract, contract lines, and invoiceable transactions. It introduces usability enhancements that streamline invoice management, editing, and validation—reducing clicks and improving clarity.| |
| Performance |**Performance improvements across processes** <br><br> This feature enables asynchronous processing of the following long running processes: Close a quote as won, confirm a contract, create/confirm/revise invoices, copy price list, update prices on a project. If an initiated process is determined to be long-running, the user sees a banner notification and will receive an in-app notification once the process is completed.||
| Sub-contracting |**Enable Subcontracting UX enhancements for smoother navigation and insights** <br><br> This feature is behind a feature flag "Enable new subcontracting UX enhancements for improved insights and smoother navigation". When enabled, this feature delivers: A more organized main form, Enhanced subcontracting insights, Improved resource handling for smoother workflows designed to streamline navigation and boost visibility into subcontracting operations.| |
| Project Budget Management |**Column based time phasing of Project Budgets instead of row based (Private Preview)** <br><br> This feature introduces a new column-based time phasing view for Project Budgets, complementing the existing row-based layout. A dedicated tab will be added to display budget data in a columnar format, offering a clearer and more structured time-based breakdown. Available as a limited preview, with additional enhancements planned for the upcoming release wave. To enable the feature in pre-prod, please raise a support ticket with Microsoft.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing|	5530102|	Correction journal preview fails if one or more time entries can no longer be corrected|
|Pricing|	4997620|	Unable to delete Transaction Category as pricing dimension|
|Pricing|	5206990|	Product bundles cause errors with Copy Price List|
|Pricing|	5516935|	Material usage log: Unit Cost for work order products are incorrectly initialized|
|Project And Resource Management|	5278591|	Import project shows duplicate fields|
|Project Estimates|	5129793|	Imported Contract Line Detail's billing type is carried from Estimate line, instead of Contract line task setting|
|Project Operations Time Management|	4427926|	TimeEntry status shows submitted while it should be draft|
|Project Planning And Tracking|	4605239|	Unable to access task record through "Team" tab|
|Project Planning And Tracking|	5223364|	Error when creating a team member that has more than one order line resource category associated|
|Project Planning And Tracking|	5572782|	Disable the copy project button for externally scheduled project when new experience is not enabled|
|Sales|	5362696|	PBB - Default Currency is set to USD Instead of Contract Currency|
|Sales|	5365268|	Project Contract Customer and Contract Line Customer currency should default from the Contract Currency|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
