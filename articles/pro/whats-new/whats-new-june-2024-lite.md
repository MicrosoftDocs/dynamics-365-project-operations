---
title: What's new June 2024 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the June 2024 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: mohitmenon
ms.date: 06/14/2024
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new June 2024 - Project Operations Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing._

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.105.0.5.

## Features included in this release
No new features are included in this release for the Core deployment.

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Project Planning and Tracking|	3544700|	Project Save fails and you see the "The action on an assignment failed because it tried to update a nonexisting assignment." error when more than 5,000 assignments are updated or deleted.|
|Billing and Pricing|	3698404|	Price List Validations fail when creating Quote from opportunity.|
|Billing and Pricing|	3714531|	Actuals grid not calculating currency exchange rate properly.|
|Billing and Pricing|	3734257|	Use Transaction Date (Time zone independent) field instead of Document date during invoice creation. |
|Project Planning and Tracking|	3739067|	[PM defined project duration] Schedule API hardcodes 8 hours/day for duration field.|
|Sales|	3740721|	Estimated Cost Fields on the project can be updated manually via flow or API.|
|Project Planning and Tracking|	3795066|	Online: In GCC, users with a G3 or G5 license can't go to the Project App (they see a license error) and on the Project view, the left-hand nav is missing.|
|Approvals|	3807887|	Create new approval sets when reapproving entries with failed approval sets.|
|Time Management|	3843424|	Time entry of type Absence was created on the day before.|
|Billing and Pricing|	3877772|	Recalculate Totals silently fail when there are more than 50,000 records.|
|Project Planning and Tracking|	3880154|	Time out due to long running RefreshTeam request, while assigning a resource to multiple tasks.|
|Project Management|	3887432|	Online: PfW Risks form contains several duplicated fields (Project, Description, Mitigation Plan & Contingency Plan).|
|Sales|	3905161|	Error on project form if the new estimates tab was customized.|
|Resource Management|	3933397|	Task Wise score null for Availability Factor.|
|Billing and Pricing|	3944356|	Price records are being copied twice when closing a quote as won.|
|Approvals|	4097112|	Failed Approvals View shows processing approvals.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
