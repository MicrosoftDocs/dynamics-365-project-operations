---
title: What's new June 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the June 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 07/01/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new June 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.168.3456.2.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.48.

## Project Operations dual-write map updates

The Project Operations June 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budget Management | **Enable Multiple Project Budget Drafts** <br><br> This feature enables users to create and maintain multiple draft budget versions for a project. The feature enables comparing of alternatives to select the appropriate budget for submission and approval. To improve usability, budgets are now available in the left navigation pane for quick access and easier management of multiple budget drafts. In addition, budget actions are conveniently available next to each budget version on the Budget tab, enabling faster administration and version control.| [Project Budget Management](..//pro/budget/projectbudgetmanagement.md) |
| Time Entry | **Modern Grid as the default time entry interface** <br><br> The Modern Time Entry Grid is now the default time entry grid interface within Project Operations. This change includes enhancements that let you show or hide columns visually without losing their information. | [Modern Time Entry Grid](../time/modern-time-entry-grid.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
| Billing | 5989595 | Importing Invoice line transactions doesn't trigger recalculation on parent Invoice or Invoice. |
| Pricing | 6241494 | Role price caching creates discrepancies in cost price calculation when there's a markup over purchase price. |
| Pricing | 6269966 | When field level security is enabled on Role Price price, Quote Line Detail price isn't defaulted despite unit matching with price list. |
| Pricing | 6307015 | Deletion of estimate lines fails due to cascading delete conflict. |
| Project Estimates | 5820605 | Planned sales display in sales amount in cost currency instead of converting from sales Currency. |
| Sales | 6296854 | Fee Amount calculated field can produce negative values when base amount is zero on project-based quote lines. |
| Subcontracting | 6364896 | Estimates show $0 for contract worker booked via Schedule Board to fulfill generic resource requirement. |

## Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1125352&dbType=3&qc=3dae808611dc01dce0e761640cf6c7301b929b749fa1b4fa4a472822c2fe3ff5).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
