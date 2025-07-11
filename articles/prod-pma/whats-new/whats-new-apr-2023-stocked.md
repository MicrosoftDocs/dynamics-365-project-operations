---
title: What's new or changed in Project Operations, April 2023 for Project Operations for manufacturing
description: This article provides information about the quality updates that are available in the April 2023 release of Microsoft Dynamics 365 Project Operations for manufacturing.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# What's new or changed in Project Operations, April 2023 for Project Operations for manufacturing

_**Applies To:** Project Operations for manufacturing-based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.32

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Accounting | **Streamline cost price and sales price calculations**</br>This feature introduces improvements and consistency in several areas related to taxes including amounts including sales tax. | [Understand how cost prices, sales prices, transfer prices, and taxes work together.](/dynamics365/project-operations/project-accounting/understand-cost-price-sales-prices-transfer-price-taxes) |
| Project Management | **Cross company data sharing**</br>Cross company data sharing fills the gap between AX 2009, AX 2012, and Microsoft Dynamics 365 finance and operations apps. Virtual company setup information sharing was possible in earlier versions but removed from finance and operations apps, causing upgrade issues. Now, Project Operations tables support virtual companies finance and operations apps as part of a global release. | [Tables supported for duplicate record data sharing.](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-tables) |

## Quality updates

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=787268).


## Removed and deprecated features

The [Removed or deprecated features in Project Operations](../../whats-new/removed-depreciated-features-project.md) article describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature isn't in active development and might be removed in a future update.

A deprecation announcement appears in the [Removed or deprecated features in Project Operations](../../whats-new/removed-depreciated-features-project.md) article 12 months before any feature is removed from the product.

For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time is less than 12 months. Typically, these changes are functional updates that must be made to the compiler.

| Feature area | Functionality | 
| --- | --- | 
| Project Accounting | Project management and accounting **Always create adjustment transaction parameter** is removed. 
| Project Accounting | Project management and accounting **Use adjustment date as new project date parameter** is removed. |
