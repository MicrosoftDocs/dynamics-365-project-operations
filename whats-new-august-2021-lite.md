---
title: What's new August 2021 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the August 2021 release of Project Operations lite deployment.
author: sigitac
ms.date: 08/10/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new August 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.13.0.152

## Features included in this release

The following features are included in this release:

- Approval sets. Approval sets group time, expense, or material usage approval requests together into smaller subsets of operations. This grouping allows approvals to be processed in order by Project and allows for retrying and sequencing. Grouping improves the reliability and traceability of approval processing for large volumes of approvals.

## Quality updates

###

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2295625 | Milestone name must be copied from invoice schedule to invoice line detail |
| Billing and pricing | 2316323 | Discount should not be editable on proforma invoice in Project Operations for resource based scenarios |
| Opportunity management | 2338619 | Opportunity and Quote Business Rule must be invoked on forms only. |
| Resource management | 2316523 | Using "Send request" from a resource requirement with a role attached must not throw an error |
| Resource management | 2326885 | Creating Resource Requirement through project must not throw an error |
| Time and expense | 2335584 | Deprecated task flows in the time entry |
| Time and expense | 2336884 | Copy Week time entry ribbon button must work not only for current user |
