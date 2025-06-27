---
title: What's new January 2025 - Project Operations Core deployment
description: This article provides information about quality updates that are available in the January 2025 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 01/15/2025
ms.reviewer: johnmichalak
---

# What's new January 2025 - Project Operations Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.123.0.X.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budgeting |**Enable reimport of estimates/quote/contract on a revised budget version.** <br><br> As part of this enhancement, you can reimport estimates into a revised budget version which is in the draft stage. To reimport the estimates, quote, or contract, revise the budget version and then reimport.| [Create a project budget from estimates](../budget/create-project-budget-from-estimates.md) |		


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Subcontracting|	4339657| Unbilled sales actuals not found when chargeable task is added to contract line after vendor invoice is confirmed.|
|Subcontracting|	4382804| When closing quote as won, an **Object reference not set to an instance of an object** error occurs.|
|Billing and Pricing|	4473237| The Extended amount on retainer invoice lines get set to 0 after invoice recalculation.|
|Time Entry|	4475300| A previously **Deactivated** bookable resource role can still be used within copy week functionality.|
|Subcontracting|	4481246| Actual reevaluation: Vendor Invoice Cost Actuals are missing fields.|
|Sales|	4481592| Product lines not showing correct tab when an invoice is created.|
|Subcontracting|	4481635| Actual Reevaluation: All Vendor Invoice Actuals are reversed when a task deleted.|
|Sales|	4486054| Pressing recalculate on quote sets quote lines to 0 if there are no Quote Line details.|
|Project Estimates|	4486190| The **An item with the same key has already been added** message appears when opening Time-phased Estimates tab.|
|Resource Management|	4488867| Adding team member directly in CDS for PSCore doesn't call PSS Create Team Member API.|


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
