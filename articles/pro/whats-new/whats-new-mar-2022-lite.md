---
title: What's new March 2022 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the March 2022 release of Project Operations lite deployment.
author: sigitac
ms.date: 03/14/2022
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new March 2022 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.30.0.99
##

## Features included in this release

- Subcontracting: vendor invoice creation and matching experiences.


## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Time and expense | 2388011| Show reject comments to time entry submitters at bulk approval |
| Project planning and tracking | 2495294 | Project details must not be editable in Task details form |
| Billing and pricing | 2499605 | Contract Milestones created via Quote Milestones are incorrectly marked as read-only in the UI |
| Project planning and tracking | 2506050 | [Schedule APIs] Operation set stay pending for 1 hour if no change to save and falsely marked as Failed after, should be complete right away |
| Billing and pricing | 2507401 | Contracting unit is defaulted incorrectly on Project due to incorrect caching |
| Billing and pricing | 2541660 | Sales Order Creation Validation in Dual Write should be for Project-Based Orders only |
| Billing and pricing | 2552745 | Tax not split between customers with split billing rules |
| Billing and pricing | 2558859 | Improved error messages when setting up Pricing Dimensions |
| Billing and pricing | 2558933 | Import from Project Estimates fails when customer adds msdyn_project as a Pricing Dimension |
| Billing and pricing | 2559101 | Project Parameter deletion is not blocked and causes issues |
| Opportunity management | 2570390 | DualWrite Plugin enforces the account type on Quote/Order/Opportunity to be &quot;Customer&quot; even though they are not work-based (ie, PSA quote) |
| Billing and pricing | 2586097 | Split billed cost actuals not reversed when project removed from project contract line |
| Billing and pricing | 2589619 | Tax on write in material is propagating to unbilled sales actuals and hence to invoice |
| Opportunity management | 2594015 | Unable to close quote as won for customer&#39;s with Net60 payment term |
| Project planning and tracking | 2595841 | Project for the Web: Users are shown an error about missing msdyn_actualstart when trying to create a new resource request |
| Time and Expense | 2602511 | Time Entries &quot;Rejected by&quot; showing as System instead of the named user. |
| Time and Expense | 2602528 | A project approver is able to approve time on projects where they are not flagged as an approver |
| Billing and pricing | 2608550 | It is possible to confirm a correction invoice that does not have changes from the original |

## Removed and depreciated features
The [Removed or deprecated features in Project Operations](https://docs.microsoft.com/en-us/dynamics365/project-operations/whats-new/removed-depreciated-features-project) topic describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature is not in active development and may be removed in a future update.

Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Project Operations](https://docs.microsoft.com/en-us/dynamics365/project-operations/whats-new/removed-depreciated-features-project) topic 12 months prior to the removal.

