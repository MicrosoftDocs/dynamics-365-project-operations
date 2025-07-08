---
title: What's new March 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the March 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new March 2021 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.8.0.91 
- Project management and accounting on Dynamics 365 Finance environment version 10.0.16 

## Quality updates

### Project Operations on Dataverse


| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2133873 | Fixed the display of **Unit Sales Price** currency symbol in the **Expense Estimates** grid. |
| Billing and pricing | 2174616 | When a quote is won, the contract custom pricelist is referenced on contract line details that are copied from the quote. |
| Opportunity Management | 2167475 | Fixed tax amount in the correction invoice that originated an unbilled actual entry. |
| Opportunity Management | 2176285 | Tax amount must not be copied from sales contract/quote line details to cost contract/quote line details. |
| Opportunity Management | 2188079 | Split billing rule must not be created for contracts that are not work-based. |
| Planning and Tracking | 2125274 | **Project Dual Write Map** attribute for **Project Start Date Mapping** updated from **msdyn\_taskearlieststart** to **msdyn\_actualstart**. |
| Planning and Tracking | 2138853 | Project copy function updated to ensure expense estimate lines that reference tasks are copied to the destination project. |
| Planning and Tracking | 2154306 | Fixed issues with deleting expense estimates in Project Operations for resource-based scenarios. |
| Planning and Tracking | 2173259 | Project copy function updated to ensure it doesn't display **Copying WBS** error message in certain scenarios. |
| Time and Expense | 2148910 | Fixed display issue with the **Edit Entry** page in the **Time Entry** grid. |
| Time and Expense | 2159798 | Tightened controls to ensure approved expense entries can't be edited. |

### Project management and accounting on Dynamics 365 Finance

For more information, see [What's new January 2021 - Project Operations Integrated with ERP](whats-new-jan-2021-resource-based.md).

## Regulatory updates

For information about regulatory updates for finance and operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). Another way to learn about regulatory updates is to sign in to LCS and view the planned regulatory updates using the issue search tool. Issue search lets you search by country/region, type of feature, and release.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
