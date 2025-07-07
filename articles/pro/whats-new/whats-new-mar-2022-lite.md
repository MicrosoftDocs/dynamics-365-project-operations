---
title: What's new March 2022 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the March 2022 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new March 2022 - Project Operations Core deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.30.0.99

## Features included in this release

- Subcontracting: Vendor invoice creation and matching experiences

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Time and expense | 2388011 | Show rejection comments to time entry submitters during bulk approval. |
| Project planning and tracking | 2495294 | Project details must not be editable on the **Task details** page. |
| Billing and pricing | 2499605 | Contract milestones that are created from quotation milestones are incorrectly marked as read-only. |
| Project planning and tracking | 2506050 | The operation set stays pending for one hour if there is no change to save. The set is then falsely marked as **Failed**, whereas it should be completed immediately. |
| Billing and pricing | 2507401 | Default contracting units are incorrectly entered on projects because of incorrect caching. |
| Billing and pricing | 2541660 | **Sales Order Creation Validation** in dual-write should be for project-based orders only. |
| Billing and pricing | 2552745 | Tax isn't split between customers who have set up split billing rules. |
| Billing and pricing | 2558859 | Improved error messages when pricing dimensions are set up. |
| Billing and pricing | 2558933 | **Import from Project Estimates** fails when **msdyn\_project** is added as a pricing dimension. |
| Billing and pricing | 2559101 | Project parameter deletion isn't blocked and causes issues. |
| Opportunity management | 2570390 | The dual-write plug-in forces the account type on quotations, orders, and opportunities to be **Customer**, even when that account type isn't correct. |
| Billing and pricing | 2586097 | Split billed cost actuals aren't reversed when a project is removed from a project contract line. |
| Billing and pricing | 2589619 | Tax on write-in material is propagated to unbilled sales actuals and the invoice. |
| Opportunity management | 2594015 | A quotation can't be closed as won for customers who have **Net60** payment terms. |
| Project planning and tracking | 2595841 | In Project for the Web, users receive an error message about a missing **msdyn\_actualstart** when they create a new resource request. |
| Time and Expense | 2602511 | The **Rejected by** field for time entries shows **System** instead of a named user as the rejector. |
| Time and Expense | 2602528 | A project approver can approve time on projects where they aren't listed as an approver. |
| Billing and pricing | 2608550 | A correction invoice can be confirmed even if there are no changes to the original. |

## Removed and deprecated features

The [Removed or deprecated features in Project Operations](../../whats-new/removed-depreciated-features-project.md) article describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature isn't in active development and might be removed in a future update.

A deprecation announcement will be appear in the [Removed or deprecated features in Project Operations](../../whats-new/removed-depreciated-features-project.md) article 12 months before any feature is removed from the product.
