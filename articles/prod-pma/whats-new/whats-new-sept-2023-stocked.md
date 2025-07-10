---
title: What's new or changed in Project Operations, September 2023 for Project Operations for manufacturing
description: This article provides information about the quality updates that are available in the September 2023 release of Microsoft Dynamics 365 Project Operations for Project Operations for manufacturing.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# What's new or changed in Project Operations, September 2023 for Project Operations for manufacturing

_**Applies To:** Project Operations for Project Operations for manufacturing-based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.36

## Features converted to parameters

The following table lists the features that are converted to parameter in version 10.0.36. These features can't be enabled from  [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) and these are controlled by the parameters.

| Feature name | Module | More information|
| --- | --- | --- |
|Select project invoice proposal by funding source.|Project management and accounting|This feature has been removed from feature management and moved to a parameter under the Contract tab of Project management and accounting parameters.|
|Enable the Invoice summary for Project invoice proposals and Project invoices.|Project management and accounting|This feature has been removed from feature management and moved to a parameter under the Invoice tab of Project management and accounting parameters. |

## Quality updates

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=831854).

### Features deprecated/removed in this release

This section describes features that have been removed, or that are planned for removal from Project Operations in this release.

- A _removed_ feature is no longer available in the product.
- A _deprecated_ feature isn't in active development and might be removed in a future update. 

| Feature name | Reason for deprecation/removal | More information |
| --- | --- | --- |
|Project management and accounting adjustment parameter for **Invoiced**|Transactions are much more difficult to audit if they're adjusted after they have been invoiced. This behavior causes confusion for the small number of users who use this functionality.|[Project management and accounting adjustment parameter for **Invoiced**](/dynamics365/project-operations/whats-new/removed-depreciated-features-project#project-management-and-accounting-adjustment-parameter-for-invoiced)|
|Project management and accounting **Allow for projects with multiple funding sources** parameter|This parameter was originally added before feature management was available. However, it's no longer required, because the functionality can now be safely enabled for sales orders and multiple funding sources. Multiple funding sources should now always be optionally configurable in the project contract.|[Project management and accounting **Allow for projects with multiple funding sources** parameter](/dynamics365/project-operations/whats-new/removed-depreciated-features-project#project-management-and-accounting-allow-for-projects-with-multiple-funding-sources-parameter)|

For more information, see [Removed or deprecated features in Dynamics 365 Project Operation](/dynamics365/project-operations/whats-new/removed-depreciated-features-project#project-management-and-accounting-use-adjustment-date-as-new-project-date-parameter).
