---
title: What's new February 2024 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the February 2024 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: 
ms.author: tulsijhaveri
---

# What's new February 2024 - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.91.0.95.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Resource Management | **Get recommendations for resources to staff as team members based on their past relevant experience**<br><br>Allows Project Managers and Resource Managers to receive suggestions for who to staff as a project team member based on relevant experience. This feature will eventually also consider factors such as Cost, Availability, Utilization, and Skill-match. | [Prerequisites to use resource recommendations (preview)](../..//resource-management/getting-started-with-resource-recommendations.md) |
| Pricing | **Cost plus pricing – Sales/Billing**<br><br>This feature allows customers of Dynamics 365 Project Operations to select more pricing methods or calculations when setting up role prices. The sales pricing methods supported for roles are price per unit (default), at transaction cost, or markup/markdown of the transaction cost. This feature only applies to Sales/Billing price lists. | [Set up labor bill rates](../pricing-costing/set-up-labor-bill-rate-sales.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3292863 | Material Estimates aren't priced based on their required date. |
| Billing and Pricing | 3509255 | Invoice created from a contract without a price list has total amount as 0. |
| Billing and Pricing | 3581717 | User is able to Import from estimates associated to the Project even if the Contract is confirmed. |
| Subcontracting | 3613708 | Journal line cost type and actual created from it aren't external when created manually. |
| Billing and Pricing | 3682737 | Invoice Line Details calculations not triggered when values are updated via workflow. |
| Project Contract | 3690545 | Contract performance Billed amount, cost incurred, and Gross margin numbers are zero. |
| Billing and Pricing | 3703686 | Begin and End Dates don't reflect when msdyn_begin/msdyn_enddate is updated. |
| Billing and Pricing | 3704338 | Quote recalculate doesn't find price overrides scoped to customers. |
| Project Budgeting | 3752286 | Fix Time Zone Issue with Budget Line Distribution across Budget Period Lines. |

