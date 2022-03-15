---
title: What's new March 2022 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the March 2022 release of Project Operations lite deployment.
author: sigitac
ms.date: 03/15/2022
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new March 2022 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.30.0.99

## Features included in this release

- Subcontracting: Vendor invoice creation and matching experiences


## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Time and expense | 2388011| Show reject comments to time entry submitters during bulk approval. |
| Project planning and tracking | 2495294 | Project details must not be editable on the **Task details** page. |
| Billing and pricing | 2499605 | Contract milestones that are created from quote milestones are incorrectly marked as read-only. |
| Project planning and tracking | 2506050 | Operation set stays pending for one hour if there is no change to save and then falsely marks the set as **Failed**, when it should be completed immediately. |
| Billing and pricing | 2507401 | Contracting unit defaults incorrectly on projects because of incorrect caching. |
| Billing and pricing | 2541660 | **Sales Order Creation Validation** in dual-write should be for project-based orders only. |
| Billing and pricing | 2552745 | Tax isn't being split between customers who have split billing rules set up. |
| Billing and pricing | 2558859 | Improved error messages when setting up pricing dimensions. |
| Billing and pricing | 2558933 | **Import from Project Estimates** fails when **msdyn\_project** is added as a pricing dimension. |
| Billing and pricing | 2559101 | Project parameter deletion isn't blocked and causes issues. |
| Opportunity management | 2570390 | Dual-write plug-in enforces the account type on quotes, orders, and opportunities to be **Customer** even when that isn't correct. |
| Billing and pricing | 2586097 | Split billed cost actuals aren't reversed when a project is removed from project contract line. |
| Billing and pricing | 2589619 | Tax on write-in material is propagating to unbilled sales actuals and the invoice. |
| Opportunity management | 2594015 | Unable to close a quote as won for customer's with a **Net60** payment term. |
| Project planning and tracking | 2595841 | In Project for the Web, users are shown an error about missing **msdyn\_actualstart** when they create a new resource request. |
| Time and Expense | 2602511 | The **Rejected by** field for time entries is listing **System** as the rejector instead of the named user. |
| Time and Expense | 2602528 | A project approver can approve time on projects where they aren't listed as an approver. |
| Billing and pricing | 2608550 | A correction invoice can be confirmed even if there are no changes from the original. |


## Removed and depreciated features
The [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) topic describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature is not in active development and may be removed in a future update.

Before any feature is removed from the product, the deprecation notice will be announced in the [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) topic 12 months prior to the removal.

