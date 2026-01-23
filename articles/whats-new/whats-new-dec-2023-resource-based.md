---
title: What's new December 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the December 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: tulsijhaveri
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 01/23/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak 
ms.author: dishantpopli
---

# What's new December 2023 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.89.0.15.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.37.

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Proforma Invoicing | **Ability to select and revise specific transactions in an invoice.** This feature improves usability and performance of the invoice correction process. Users can select a subset of the transactions for correction without needing to revise the entire invoice, which leads to efficient and shorter invoicing cycles. | [Revise (correct) project invoices](../proforma-invoicing/revise-project-invoices.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality Update** |
| --- | --- | --- |
| Project Planning and Tracking | 3655580 | Unsaved alert shows on project form when feature is disabled and duration fields are hidden. |
| Project Planning and Tracking | 3647289 | Create error log when user doesn't have permissions to async operation entity and can't query the system jobs. |
| Project Planning and Tracking | 3662968 | Create error log when user is missing any OOB privilege and save operation fails. |
| Project Planning and Tracking | 3647295 | Create PSS Error log when the convert project fails. |
| Project Planning and Tracking | 3349866 | Project app user is missing readAccount privilege. |
| Project Planning and Tracking | 3615118 | Project is stuck in Copying/Importing/Converting status if PSS failed to update project status to Failed due to permission issue. |
| Project Planning and Tracking | 3648246 | Plugin Deprecated: Microsoft.Dynamics.ProjectServiceCoreSandbox.Plugins.Plugins.PublishToEventHub.PostOperationUserUpdateEvent |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=838613).
