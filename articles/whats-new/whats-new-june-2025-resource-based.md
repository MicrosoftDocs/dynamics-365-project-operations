---
title: What's new June 2025 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the June 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 07/07/2025
ms.reviewer: johnmichalak

---

# What's new June 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.142.0.166.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.44.

## Project Operations Dual-write maps updates

The following table shows the Dual-write maps that are modified or added in the Project Operations June 2025 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Integration entity for project transaction relationships (msdyn_transactionconnections) | 1.0.0.1 | Latest version updated  |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Procurement and Inventory |**Enable stocked products usage for project operations integrated deployments**. <br><br> This feature is seamlessly integrated with Microsoft Dynamics 365 Finance. It lets users manage stocked products, create purchase orders and subcontracts, consume stock for projects, and use stocked products in project estimates, quotations, and contracts in Dataverse.| [Manage stocked products on integrated deployments](../procurement/enable-stocked-products-integrated.md) |
| Actuals |**Use actuals synchronization and reconciliation**. <br><br> This feature helps you identify and address integration challenges that are related to project actuals and transaction connections. Those challenges include dual-write synchronization issues. You can also initiate a resynchronization of actuals or transaction connections. This resynchronization facilitates the generation and posting of integration journal lines.| [Use actuals synchronization and reconciliation](../troubleshooting/project-operations-integration/manage-actuals-reconciliation.md) |
| Financials |**Use financial tags for project financial transactions**. <br><br> Financial tags enable organizations to track user-defined fields on accounting entries that are posted to the general ledger. Therefore, they don't have to create financial dimensions that contain values that aren't reusable. Financial tags on posted transactions can| [Use financial tags for project financial transactions](../project-accounting/financial-tags-for-project-financial-transactions.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing| 4655493| Invoice can't be confirmed when the total amount is negative, and a new retainer is raised on the same invoice. |
|Billing and Pricing| 4872141| Journal line not posted when approval is canceled, leaving the created actuals unchanged without the adjustment status. |
|Billing and Pricing| 4995210| Invoice Line without name ignores chargeability when calculating amount. |
|Billing and Pricing| 5024102| Trying to mark the contract line as "Ready to invoice" in billing hub results in "Billing status can't be updated on a contract line that isn't product-based."|
|Billing and Pricing| 5054756| Origin field on sales estimate line should be allowed to update from null. |
|Billing and Pricing| 5079606| Script error when selecting Project Task on a time entry correction journal. |
|Billing and Pricing| 5124144| Can't Delete Recalled Time Entries Associated with Revised Invoices. |
|Project Budgeting| 4829338| Unable to see dropdown values in Transaction Category field. |
|Sales|	5005220| Create Order throws "The contract line can't be updated directly."|
|Sales|	4926105| Invoice schedule type not validated on quote line update. |
|Project And Resource Management| 5001281| Unable to mark task as completed on integrated org. |
|Subcontracting| 4450523| Task doesn't get linked to contract line during billing setup. |
|Time Entry| 4871947| Time entry issues for associated view are now handled by updating fields that appear on this view. |
|Time Entry| 5089432| Modern Grid - Unable to create Time entries inline when working on the grid other than English. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1028749&dbType=3&qc=ce23ba904cf7dc2e2233a5d951b6a5974c350ed77aded0cd55f33a94a7cd6d84).

