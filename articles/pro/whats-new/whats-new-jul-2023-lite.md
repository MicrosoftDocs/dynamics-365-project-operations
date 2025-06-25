---
title: What's new July 2023 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the July 2023 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new July 2023 - Project Operations lite deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.74.0.59

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3252938|Check for presence of tabs before setting visibility.|
|Billing and Pricing|3349398|Null reference exception when updating/deleting custom-created estimate lines.|
|Billing and Pricing|3377810|Material transaction could get priced from category price.|
|Billing and Pricing|3432590|Update Error Message for Quote and Contract Price List Validation.|
|Billing and Pricing|3459402|Expose Journal Preview API to be invoked from customization.|
|Billing and Pricing|3459403|Expose Journal Confirm API to be invoked from customization.|
|Opportunity Management|3423900|Price list overlaps aren't validated when quote/contract price list is updated.|
|Opportunity Management|3423917|Entity price lists aren't validated when entity is changed.|
|Project Planning and Tracking|3259681|Estimates not being copied when the project is copied.|
|Project Planning and Tracking|3367034|Change Project Label name using Project Schedule API via Power Automate.|
|Resource Management|3209488|Adding Named Team Members to a Project For Non-Stocked Scenarios is incorrectly defaulting the TM's owning company.|
|Resource Management|3477979|Project Operations Package Deployment failing in UR35 Integrated Org.|
|Subcontracting|3236886|Unbilled Sales created with price zero during Vendor Invoice Confirmation when currency of contract is different from VI's currency.|
|Subcontracting|3338245|Posting vendor invoice fails when lines include Procurement category with category type Item.|
|Subcontracting|3445436|When a Bookable Resource doesn't have a specified Worker Type, an incorrect WorkerType is displayed on the Team tab of Project.|
|Time and Expense|3284355|No receipt is available for a submitted expense..|
