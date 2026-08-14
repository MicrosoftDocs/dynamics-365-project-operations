---
title: What's new August 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the August 2026 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 08/14/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new August 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.170.3494.5.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.48.

## Project Operations dual-write map updates

The Project Operations August 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management | **Bulk updates on the task grid** <br><br> This feature enables users to perform bulk updates on tasks within the task grid. Users can select multiple tasks by using Ctrl + Click or Shift + Click, and then choose Bulk Update from the context menu. Currently, bulk updates support modifying the Start Date, Finish Date, % Complete, and Assignments fields for multiple tasks simultaneously. | |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing | 6514403 | Posted correction invoice is missing tax information when synced to Dataverse. |
| Billing | 6514537 | Correction invoice posting fails with an error if tax is removed. |
| Pricing | 6247963 | Incorrect price list used when you save Material Usage Logs (Cost price instead of purchase price). |
| Pricing | 6256862 | Price List isn't stamped on Journal Lines, so the price is set to Null. |
| Project And Resource Management | 6567653 | Inconsistent default values for Team Member when you copy an existing project. |

## Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1125352&dbType=3&qc=3dae808611dc01dce0e761640cf6c7301b929b749fa1b4fa4a472822c2fe3ff5).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
