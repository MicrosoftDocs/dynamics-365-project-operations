---
title: What's new December 2024 - Project Operations Core deployment
description: This article provides information about quality updates that are available in the December 2024 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 07/07/2025
ms.reviewer: johnmichalak
---

# What's new December 2024 - Project Operations Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.122.0.327.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Planning |**Enabling Enterprise Custom Columns (ETCC)** <br><br> Customers can now bring up to 10 custom columns on the task grid. These custom columns are read only. The supported formats are Text, Number, Date - Date only (not Date & time), Choice (but not yes/no fields)| |		
| Project Management |**Performance improvement in Schedule APIs for bulk operations** <br><br> As part of this feature, schedule APIs V2 now process multiple records at a time in a more efficient way that lead to over 75% improvement in performance.| |		

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Subcontracting|	3816001|	Validation added to ensure subcontract currency matches vendor currency.|
|Sales|	3819709|	Able to set or add a customer having a currency different than the contract (sales pricing).|
|Subcontracting|	3921055|	Actuals are generated with amount as zero on vendor invoices without unit price (despite a positive amount populated).|
|Project Estimates|	4152179|	Estimates OneGrid quick create form throws exception if a default unit/unit group doesn't exist.|
|Project Estimates|	4198360|	Estimate lines allow linking transaction categories that don't have an associated expense category.|
|Time Entry|	4249478|	Project Operations license doesn't grant access to Team Member App.|
|Project Estimates|	4321523|	Project estimates not respecting effective date on price overrides.|
|Project Estimates|	4360880|	Project estimate updates feature breaks legacy estimates workflow customizations.|
|Sales|	4396988|	Fix 'Project Contract is Missing' error thrown for nonadmin users when closing a quote as won. |
|Resource Management|	4413953| **An unexpected error occurred** or **Object reference not set to an instance of an object.** when trying to book a project resource from the schedule board without using team member generated requirement.|
|Billing and Pricing|	4424610|	Incorrect error message displayed when attempting to price a transaction that lacks a unit.|
|Subcontracting|	4435263|	PODW: Validation added to prevent vendor invoices from being auto confirmed without any vendor invoice lines.|


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
