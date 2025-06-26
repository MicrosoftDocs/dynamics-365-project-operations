---
title: What's new or changed in Project Operations, February 2024 for manufacturing
description: This article provides information about the quality updates that are available in the February 2024 release of Microsoft Dynamics 365 Project Operations for manufacturing.
author: tulsijhaveri
ms.date: 2/20/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: tulsijhaveri
---

# What's new changed in Project Operations, February 2024 for manufacturing

_**Applies To:** Project Operations for manufacturing-based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.38

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Sales | **Cost plus pricing - Quotes**<br><br>Introducing a Price Override button on the Quote Line Detail form to enable quick and easy editing of role prices, while remaining within the context of quote line detail. This button provides new functionality that reduces unnecessary clicks and streamline your Role price editing process. | [New Quote form experience](/dynamics365/project-operations/sales/quotes-new-form) |

## Quality updates
### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=857683).

## Features turned on by default in upcoming release
The following table lists the features that are turned on by default in version 10.0.39. Most features that are automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that are automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they're added. Features aren't automatically enabled in less than one year unless they're determined to be essential. 

| **Feature name** | **Enable date** | **Feature added** | **Feature state** | **Module** |
| --- | --- | --- | --- | --- |
| Allow item requirements with multiple funding sources for Project Operations manufacturing | January 28, 2024 | March 31, 2022 | Enabled by Default | Project Financials |
| Multi-select posted project transactions for adjustments and credit adjustment notes | January 28, 2024 | November 9, 2023 | Enabled by Default | Project Financials |
| Performance improvement to filter by project for project invoice proposals with billing rules | January 28, 2024 | November 9, 2023 | Enabled by Default | Project Financials |

## Features converted to parameters

The following table lists the features that are converted to a parameter in version 10.0.39. These features can't be enabled from [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) and controlled using parameters.

| **Feature area** | **Feature flag name** | **More information** |
| --- | --- | --- |
| Project Financials | Enable the Invoice summary for Project invoice proposals and Project invoices | [Project invoicing](/dynamics365/finance/accounts-payable/project-invoicing) |
| Project Financials | Select project invoice proposal by funding source | [Creating invoice proposals](/dynamics365/finance/accounts-payable/project-invoicing#creating-invoice-proposals) |

## Other features state changes

The following table lists the features that have feature state changes from version 10.0.39 onward.

| **Feature name** | **Feature added** | **Feature state** | **Module** |
| --- | --- | --- | --- |
| Use procurement categories in Project Operations for resource based/non-stocked scenarios | March 31, 2022 | Released | Procurement |
