---
title: What's new February 2025 - Project Operations Lite deployment
description: This article provides information about quality updates that are available in the February 2025 release of Microsoft Dynamics 365 Project Operations Lite deployment.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 02/20/2025
ms.reviewer: johnmichalak
---

# What's new February 2025 - Project Operations Lite deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.124.0.1450.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Mobile App** <br><br> Project team members on Lite and resource/Non stocked-based deployments of Project Operations now have a new mobile application based on Microsoft Power Apps. The new mobile app helps them log time, keep track of submitted entries, and view work assigned to them. | [Time Entry Mobile App](../../time/time-entry-mobile-app-overview.md)  |
| Sales |**Time phasing of Sales Estimates** <br><br> The Time phasing of prices feature provides visibility into price fluctuations over time within project quote lines and project contract lines. Nested quote line details display price changes phased out on a weekly basis, allowing you to track adjustments due to price overrides or multiple price lists.| [Estimate a project quote line](../../sales/create-estimate-quote-line.md) <br> [Estimate a project contract line](../../sales/create-estimate-contract-line.md) |
| Invoicing |**Progress Billing in Billing hub** <br><br> | [Progress billing within Billing Hub](../../proforma-invoicing/billing-hub.md)  |


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3272365|	Updated Time & Material Backlog Filters to only reflect actuals that can be invoiced|
|Project Planning|	3740986|	Project.AttributeMsdyn_MSProjectDocument is now blocked by EntityGuard at Create|
|Billing and Pricing|	4152179|	Estimates OneGrid quick create form throws exception if no default unit/unit group exist|
|Billing and Pricing|	4187521|	Invoice revision copies fields that cause privilege exception|
|Billing and Pricing|	4211979|	Invoice Line Detail correction field can be true even when original Invoice Line Detail is blank|
|Approvals|	4438571|	Project Approver role lacking sufficient privileges to view approvals|
|Subcontracting|	4481246|	Actual Re-evaluation: Vendor Invoice Cost Actuals Are Missing Fields|
|Subcontracting|	4481635|	Actual Re-evaluation: All Vendor Invoice Actuals Are Reversed When Task Deleted|
|Subcontracting|	4484351|	Cannot correct actuals from cancelled vendor invoice|
|Billing and Pricing|	4498838|	On the price override bulk create dialog, "Effective date" is impacted by local time zone|
|Billing and Pricing|	4508856|	Changing Project on Contract Line fails due to lack of permissions for msdyn_longrunningjobstatus|
|Billing and Pricing|	4511507|	Disallow changes to Project invoice status from confirmed (or paid) to "In review" or any OOB status|
|Billing and Pricing|	4511677|	Handle error when transaction classification is missing on the Invoice Line Detail when confirming invoice|
|Time Enty|	4521147|	Modern Time Entry Grid text still shows up in English in non-eng base language environments|
|Billing and Pricing|	4524095|	Quantity is cleared on journal line main form open|
|Sales|	4529109|	Invoice schedule type is not re-defaulted when billing method is updated on quote line|
|Project Budgeting|	4546764|	Fix unit conversion on merging of budget lines during budget import & summarization|
|Project and Resource Management|	4594360|	When Allow percent complete is No, and when a task is marked as completed, schedule variance is not getting updated.|
|Billing and Pricing|	4606728|	Unable to view milestones backlog in Billing hub|
|Sales|	4625154|	Recalculate button not is working on Quotes and Contracts|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
