---
title: What's new May 2025 - Project Operations Core
description: This article provides information about quality updates that are available in the May 2025 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new May 2025 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.141.0.975.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**New Time Entry Calendar View** <br><br> Team members can now interact with their time entries in a new calendar view. This view allows changing timelines to summarize time entries between Daily, Weekly, and Monthly horizons. In addition, the Time Entry Calendar comes with a Charts section that compares hours logged with target working hours and even allows users to filter time entries by status or type (Overtime, Vacation, etc.).| [New Time Entry Calendar (Preview)](../../time/time-entry-calendar.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Approvals|	4606055|	Duplicate actuals generated for same time entry when actuals get reevaluated and approval gets canceled.|
|Approvals|	5060891|	External description is lost when submitting time, expense, material usage, or entry journal.|
|Billing and Pricing|	4769472|	Recurring Invoice Schedule - Duplicate Transactions when multiple records have the same Invoice Run Date.|
|Billing and Pricing|	4789534|	Can't Update Actuals Created By Dynamics 365 Field Service.|
|Billing and Pricing|	4826053|	Basis Price field values are inconsistent while copying from a source, only when the Cost Plus Pricing feature is enabled.|
|Billing and Pricing|	4840276|	Time phased estimate doesn't evaluate the right cost price when price overrides are used along with exchange rate.|
|Project and Resource Management|	4916438|	Show calendar tab by default for Project Operations users.|
|Sales|	4713365|	Quote or Contract Line Details of type "Time" shouldn't have units from different unit groups.|
|Sales|	4895890|	Unable to change invoicing status of progress based billing milestones using action buttons.|
|Sales|	4902277|	"The contract line can't be updated directly" error when trying to delete a project contract.|
|Sales|	5083058|	Chargeability on categories not honored while importing estimates.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
