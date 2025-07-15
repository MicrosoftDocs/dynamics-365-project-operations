---
title: What's new August 2024 - Project Operations Core
description: This article provides information about quality updates that are available in the Aug 2024 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new August 2024 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.108.0.15.

## Features included in this release

No new features in this release of Project Operations Core. 


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3546798|	A scope with nonmatching currency can be added to price overrides.|
|Project Planning and Tracking|	3742761| Add work hour template to the list of restricted attributes when copying data from source project.|
|Billing and Pricing|	3802977|	Hide the **Price Override** button for cost record.|
|Billing and Pricing|	3883056|	Rounding precision isn't being honored with primary unit creating incorrect actuals.|
|Project Budget Management|	3929679|	In Draft mode of budget grid, the Task field is showing tasks of ALL project not just the current project.|
|Billing and Pricing|	3941977|	Can't deactivate a price list with overrides.|
|Sales|	3981724|	Duplicate contract split billing rules can be created.|
|Subcontracting|	4118084| Actuals created from VI lines don't populate "Bookable resource" field.|
|Sales|	4161956|	Syncing from sales to cost when updating Quote Line Details prevents the update of totals on the Quote Line.|
|Billing and Pricing|	4173215|	Don't allow deleting contract lines with unbilled invoice lines.|
|Subcontracting|	4181897|	Default expense category on the expense Quick Create form when subcontract and subcontract line fields are selected.|
|Time Entry|	4186684|	Time Off entry doesn't get cleared from resource calendar when time entry type is changed to Work or Overtime.|
|Billing and Pricing|	4192197|	Negative actuals don't have replacing Unbilled Sales actuals created on correction invoice confirmation.|
|Billing and Pricing|	4199581|	Script error occurs when clicking on Invoiceable backlog in Billing hub.|
|Billing and Pricing|	4211979|	Invoice Line Detail (ILD) correction field can be true even when original ILD is blank.|
|Billing and Pricing|	4212681|	Can have an applied retainer on invoice after retainer is refunded.|
|Project Budget Management|	4229374|	Group by capability doesn't work in project budget line subgrid.|
|Time Entry|	4231555|	Fix entity name regression that caused issues with time entry deletion and workflow modification.|
|Sales|	4300829|	Move PBB Confirm Logic Causes Invoice Confirmation Failure > 5000 ILDs.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
