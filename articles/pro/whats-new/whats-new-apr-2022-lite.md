---
title: What's new April 2022 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the April 2022 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new April 2022 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.41.0.45

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Time and expense | 2573900 | The **Modern Approval** feature must be enabled by default. |
| Billing and pricing | 2603313 | Fixed a duplicate record error that prevented quote and contract lines that have a product from being added. |
| Deployment and configuration | 2611368 | Customers must be able to add up to five custom entities to the solution by using the modern app designer. |
| Time and expense | 2628285 | Fixed an issue that affected the ability to set the correct resource category during time entry import. |
| Opportunity management| 2628815 | Update the character limit of the quote line detail description to match the character limit of the task subject, so that import succeeds for tasks where the subject is longer than 100 characters. |
| Time and expense| 2629547 | The **Submitted By** field of project approvals must point to the user who submitted the record. |
| Time and expense| 2629865 | The **Copy category** field on tasks when projects are copied. |
| Time and expense| 2636463 | Fixed the filters on approvals in modern approvals forms. |
| Project planning and tracking | 2648300 | Fixed an issue that prevents the project owner from being changed. |
| Billing and pricing | 2563000 | Journal lines for an unbilled sale where the currency differs from the contract currency must not be allowed. |
