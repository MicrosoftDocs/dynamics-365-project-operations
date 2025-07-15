---
title: What's new October 2022 - Project Operations Core
description: This article provides information about the quality updates that are available in the October 2022 release of Microsoft Dynamics 365 Project Operations Core.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new October 2022 - Project Operations Core

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.57.0.176

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Planning and Tracking | **Project Operations External Scheduling**<br>The external scheduling mode lets customers natively create, update, and delete entities that are related to the work breakdown structures (WBS) by using the native Dataverse APIs, without the current limits that are enforced by Project for the Web. | [External Scheduling](/dynamics365/project-operations/project-management/external-scheduling) |
| Deployment and Configuration | <p>**Allow customers to choose the deployment type**<br>Product-driven updates (PDUs) of Project Operations are used to automatically install Project Operations Dual-write solution when Dual-write core and orchestration solutions are installed in the environment.</p><p>This feature introduces a new **Solution upgrade behavior** parameter in Project parameters. When this parameter is set to **Project Operations Core only**, PUDs will no longer automatically install Project Operations Dual-write solution, even if Dual-write core and orchestration solutions are installed in the environment. This behavior will benefit customers who plan to use Dual-write solutions to integrate sales orders into finance and operations apps, but want to use Project Operations in a Project Operations Core mode (that is, without integration into finance and operations apps).</p> | |

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2316317 | The system allows invoice to be created that have no chargeable transactions. |
| Billing and Pricing | 2737300 | Validate for Customer field availability before the form is accessed. |
| Billing and Pricing | 2744948 | Add a null check for Billing method. |
| Billing and Pricing | 2763515 | Null reference error handle when the sales contract of the invoice is missing. |
| Billing and Pricing | 2844301 | Batch invoice creation fails because of an error. |
| Billing and Pricing | 2845869 | Incorrect storage of Organization Service. |
| Billing and Pricing | 2853729 | Role and Price details are updated when Billing type is modified. |
| Billing and Pricing | 2940350 | When actuals are priced, only active price lists should be automatically entered. |
| Deployment and Configuration | 3001206 | The msdyn\_replaylogheader entity is preventing upgrades of Customer Orgs. |
| Opportunity Management | 2755582 | Null reference exceptions handle in Split Billing Rule Helper. |
| Opportunity Management | 2761477 | When split billing is used, deletion of a milestone (header) leaves orphan milestones. |
| Opportunity Management | 2767595 | When a material usage record is opened in the main form, Bookable resource for the record is changed to the currently signed-in user. |
| Project Planning and Tracking | 2790384 | The Pending OperationSet time-out is too short. |
| Resource Management | 2751560 | Inconsistent Preferred Organization Units in Resource Requirement. |
| Subcontracting | 2907231 | The process stage of vendor invoices can't advance. |
| Time and Expense | 2867363 | Records don't fall out of the Absences/Vacations for Approval view when they're queued for approval. |
| Time and Expense | 2894405 | TESA: The unused POC directory is causing compliance issues. |
