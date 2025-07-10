---
title: What's new February 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the February 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: tulsijhaveri
---

# What's new February 2024 - Project Operations Integrated with ERP

**Applies To:**  Project Operations Integrated with ERP

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.91.0.95.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.38.

## Project Operations dual-write maps updates

The following table shows the modified or added Dual-write maps in the Project Operations February 2024 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.17 | Latest version updated |
| Project Operations integration entity for hour estimates (msdyn_resourceassignments) | 1.0.0.6 | Latest version updated |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.6 | Latest version updated |

### Vendor invoice lines Dual-write map update

As part of the 10.0.38 upgrade, a new iteration of the Dual-write map is added, version 1.0.0.6, specifically for vendor invoice lines. This updated version enables the execution of intercompany vendor invoices. To enable this feature, certain integration keys were modified. If the Dual-write map for vendor invoice lines ceases to function, following these steps.

1.  Navigate to **Data Management workspace**, and locate the Dual-write maps section.
2.  On the Action pane, select the **Integration key**.
3.  Select the **Project vendor invoice line** integration key.
4.  Remove **msdyn_owningcompany** from the integration key.
5.  Ensure that **msdyn_externalinvoiceline** remains the only field for the **Vendor invoice line integration** key.
   
For a current list and versions of Project Operations Dual-write maps, see [Project Operations dual-write map versions](/dynamics365/project-operations/environment/resource-dual-write-maps).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Resource Management | **Get recommendations for resources to staff as team members based on their past relevant experience**<br><br>Allows Project Managers and Resource Managers to receive suggestions for who to staff as a project team member based on relevant experience. In future releases, this feature considers factors such as Cost, Availability, Utilization, and Skill-match. | [Prerequisites to use resource recommendations (preview)](../resource-management/getting-started-with-resource-recommendations.md) |
| Pricing | **Cost plus pricing – Sales/Billing**<br><br>This feature allows customers of Dynamics 365 Project Operations to select more pricing methods or calculations when setting up role prices. The sales pricing methods supported for roles are price per unit (default), at transaction cost, or markup/markdown of the transaction cost. This feature only applies to Sales/Billing price lists. | [Set up labor bill rates](../pricing-costing/set-up-labor-bill-rate.md) |
| Procurement | **Enable Intercompany Project Vendor invoices for resource based/non-stocked scenarios.**<br><br>Allow the user to generate intercompany vendor invoices for Project operations Project Operations Integrated with ERP based scenario.<br><br>To use this feature, Need to update the Dual-write maps for vendor invoice header and vendor invoice lines as per the documentation. | [Intercompany vendor invoice](../pro/subcontracting/intercompanyvendorinvoicefornonstockscenario.md) |
| Sales | **Cost plus pricing - Quotes**<br><br>Introducing a Price Override button on the Quote Line Detail form to enable quick and easy editing of role prices, while remaining within the context of quote line detail. This button provides new functionality that reduces unnecessary clicks and streamline your Role price editing process. | [New Quote form experience](/dynamics365/project-operations/sales/quotes-new-form) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3292863 | Material Estimates aren't priced based on their required date. |
| Billing and Pricing | 3509255 | Invoice created from a contract without a price list has total amount as 0. |
| Billing and Pricing | 3581717 | User is able to Import from estimates associated to the Project even if the Contract is confirmed. |
| Subcontracting | 3613708 | Journal line cost type and actual created from it aren't external when created manually. |
| Billing and Pricing | 3682737 | Invoice Line Details calculations not triggered when values are updated via workflow. |
| Project Contract | 3690545 | Contract performance **Billed amount**, **Cost incurred**, and **Gross margin** numbers are zero. |
| Billing and Pricing | 3703686 | Begin and End Dates don't reflect when msdyn_begin/msdyn_enddate is updated. |
| Billing and Pricing | 3704338 | Quote recalculate doesn't find price overrides scoped to customers. |
| Project Budgeting | 3752286 | Fix Time Zone Issue with Budget Line Distribution across Budget Period Lines. |

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
