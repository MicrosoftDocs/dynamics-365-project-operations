---
title: What's new February 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the February 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: tulsijhaveri
ms.date: 2/15/2024
ms.topic: article
ms.prod:
ms.reviewer: 
ms.author: tulsijhaveri
---

# What's new February 2024 - Project Operations for resource/non-stocked based scenarios

**Applies To:**  Project Operations for resource/non-stocked based scenarios

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.91.0.95.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.38.

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the Project Operations February 2024 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.17 | Latest version updated |
| Project Operations integration entity for hour estimates (msdyn_resourceassignments) | 1.0.0.6 | Latest version updated |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.6 | Latest version updated |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](https://learn.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Resource Management | **Get recommendations for resources to staff as team members based on their past relevant experience**<br><br>Allows Project Managers and Resource Managers to receive suggestions for who to staff as a project team member based on relevant experience. This feature will eventually also consider factors such as Cost, Availability, Utilization and Skill-match. | [Prerequisites to use resource recommendations (preview)](https://learn.microsoft.com/en-us/dynamics365/project-operations/resource-management/getting-started-with-resource-recommendations) |
| Pricing | **Cost plus pricing – Sales/Billing**<br><br>This feature allows customers of Dynamics 365 Project Operations to select additional pricing methods or calculations when setting up role prices. The sales pricing methods supported for roles are price per unit (default), at transaction cost, or markup/markdown of the transaction cost. This only applies to Sales/Billing price lists. | [Set up labor bill rates](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/pricing-costing/set-up-labor-bill-rate-sales) |
| Procurement | **Enable Intercompany Project Vendor invoices for resource based/non-stocked scenarios.**<br><br>Allow the user to generate intercompany vendor invoices for Project operations resource/non-stocked based scenario.<br><br>To use this feature, Need to update the Dual write maps for vendor invoice header and vendor invoice lines as per the documentation. | [Intercompany vendor invoice](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/subcontracting/intercompanyvendorinvoicefornonstockscenario) |
| Sales | **Cost plus pricing - Quotes**<br><br>Introducing a Price Override button on the Quote Line Detail form to enable quick and easy editing of role prices, while remaining within the context of Quote line detail. This button provides a new functionality that reduces unnecessary clicks and streamline your Role price editing process. | [New Quote form experience](https://learn.microsoft.com/en-us/dynamics365/project-operations/sales/quotes-new-form) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3292863 | Material Estimates are not priced based on their required date |
| Billing and Pricing | 3509255 | Invoice created from a contract without a price list has total amount as 0 |
| Billing and Pricing | 3581717 | User is able to Import from estimates associated to the Project even if the Contract has been confirmed. |
| Subcontracting | 3613708 | Journal line cost type and actual created from it are not external when created manually |
| Billing and Pricing | 3682737 | Invoice Line Details calculations not triggered when values are updated via workflow. |
| Project Contract | 3690545 | Contract performance Billed amount, cost incurred and Gross margin numbers are zero |
| Billing and Pricing | 3703686 | Begin and End Dates do not reflect when msdyn_begin/msdyn_enddate is updated |
| Billing and Pricing | 3704338 | Quote recalculate does not find price overrides scoped to customers |
| Project Budgeting | 3752286 | Fix Time Zone Issue with Budget Line Distribution across Budget Period Lines |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=857683).
