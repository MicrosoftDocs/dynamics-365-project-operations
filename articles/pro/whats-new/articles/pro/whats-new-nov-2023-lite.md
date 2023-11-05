---

title: What's new November 2023 - Project Operations Lite deployment
description: This article provides information about the quality updates that are available in the October 2023 release of Microsoft Dynamics 365 Project Operations Lite deployment.
author: tulsijhaveri
ms.date: 11/06/2023
ms.topic: article
ms.prod:
ms.reviewer:  
ms.author: tulsijhaveri
---

# What's new November 2023 - Project Operations Lite deployment

_ **Applies To:** __  Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.88.0.68.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time entry | **In-grid editability within Modern Time Entry Grid** This is a new capability that is available when a user switches to "Modern Time Entry Grid". This introduces in-grid editability of Project, Project Task and Role fields (for now) without using an "Edit Row" form. This can be done by double-clicking these fields, for "Draft", "Returned" and "Recalled" rows. Ability to edit more fields will be enabled in subsequent releases. |   |
| Project Budget Management | **Sales budgets included in Project sales budget management.** Project Operations is expanding its budget management capabilities to include sales budgets. This means you can create, approve, revise and track your sales budgets just like you do with cost budgets. Unbilled sales and billed sales actuals track against the sales budget lines. This expansion simplifies your experience by using the existing 'Enable Project Budgeting' feature flag. If you have already enabled 'Enable Project Budgeting' feature flag, you can create sales budgets along with cost budgets. In summary, Project Operations now offers unified and comprehensive budget management for both cost and sales, making it easier to manage your project budgets. | [**Project budget management overview**](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/budget/projectbudgetmanagement) |


## Quality updates 

**Project Operations on Dataverse**

| **Feature area** | **Reference number** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3457165 | Invoice can be confirmed without ProjOps confirmation business logic |
| Billing and Pricing | 3349847 | NRE in ProjOps integrated upon creating invoice with corrupted split billing rules |
| Billing and Pricing | 3445951 | Actuals re-evaluation fails for upgraded data - need split billing rule update |
| Billing and Pricing | 3234349 | Journal Line can have contract line customer that doesn't match project contract |
| Billing and Pricing | 3567544 | Quote Line Detail creation from Project Estimate Import failing. |
| Project Operations Upgrade | 3507354 | 3x Add-In for Project Desktop can connect, read, and publish to an Upgraded PO4x org |
| Project Planning and Tracking | 3572672 | Custom fields on tasks can't be updated via Dual-Write |
