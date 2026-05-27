---
title: What's new May 2026 - Project Operations Core
description: Learn about quality updates that are available in the May 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 05/27/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new May 2026 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.167.3420.4.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals |**Project Level Filtering for Approvals Agent** <br><br> The feature enables customers to decide which projects' approval records the agent should review. | |
| Project Planning |**Task Level Schedule Modes** <br><br> With task-level schedule modes, you can now override project scheduling mode on individual tasks to apply a different calculation behavior where needed. This capability gives project managers fine-grained control over scheduling without changing the project-wide setting.| |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
|Billing and Pricing|	6244539|	Status Reason field can no longer be modified on confirmed invoices|
|Billing and Pricing|	6269908|	Modern Invoice - Form Contains Unsaved Changed When PendingTransactions Amount is $0|
|Billing and Pricing|	6379494|	Modern Invoice - Pending transaction amount does not render|
|Journals|	6094351|	Time Zone Agnostic (TZA) Accounting Date is not being correctly defaulted|
|Billing and Pricing|	5727138|	Recalculate action on Quote comes up with a different cost price than from creating a Quote Line Detail|
|Billing and Pricing|	6031924|	Price is incorrectly set to $0 when recalculating Contract/Quote where no price record exists and time-phasing is enabled|
|Project And Resource Management|	6295665|	Team grid not loading automatically after project creation|
|Project Budgeting And Forecasting|	6232343|	Budget period setup is not creating the period for the selected month, instead creating one month before the end date|
|Project Budgeting And Forecasting|	6304128|	Project Budget - Import from estimates time phases the time budget lines incorrectly, with the wrong distribution|
|Project Estimates|	6111267|	Estimate line sales price is not re-defaulted after a cost price update|
|Project Estimates|	6293833|	Time phased estimates grid does not show correct currency when cost and sales currency don't match|
|Project Estimates|	6363037|	Cost Price for an estimate line should not be a required field on UI|
|Time Entry|	4662755|	Dark Mode Causes Visibility Issues in Time Entry Pages|
|Time Entry|	6020362|	Copy week causes screen flickering due to repeated backend calls|
|Project Planning And Tracking|	5860573|	Mismatch in the values between Required hours and Total Effort|
|Subcontracting|	6246178|	Aggregate Actuals does not happen for Actuals created after Vendor Invoice Auto Confirmation|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
