---
title: What's new August 2021 - Project Operations Core deployment
description: This article provides information about the quality updates available in the August 2021 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new August 2021 - Project Operations Core deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.13.0.152

## Features included in this release

The following features are included in this release:

- **Approval sets**: Approval sets group time, expense, or material usage approval requests together into smaller subsets of operations. This grouping allows approvals to be processed in a specific order by project and allows for retrying and sequencing. Grouping the requests improves the reliability and traceability of approval processing for large volumes of approvals. For more information, see [Approval sets](../../approvals/approval-sets.md).

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2295625 | The milestone name must be copied from the invoice schedule to the invoice line detail. |
| Billing and pricing | 2316323 | The discount shouldn't be editable on a proforma invoice in Project Operations for resource-based scenarios. |
| Opportunity management | 2338619 | **Opportunity** and **Quote** business rules must be invoked only on pages. |
| Resource management | 2316523 | Using **Send Request** from a resource requirement that has a role attached should not display an error. |
| Resource management | 2326885 | Creating a resource requirement through a project should not display an error. |
| Time and expense | 2335584 | Deprecated task flows in the time entry. |
| Time and expense | 2336884 | The **Copy Week** time entry button must work for more than just the current user. |
