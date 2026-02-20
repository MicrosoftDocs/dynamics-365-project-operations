---
title: What's new February 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the February 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 02/20/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new February 2026 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.163.0.65.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.46.

## Project Operations dual-write map updates

This release doesn't include updates for Project Operations dual-write maps. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Types |**Enable investment project for Project Operations integrated with ERP** <br><br> When you enable investment projects in Microsoft Dynamics 365 Project Operations integrated with ERP systems, you can manage capital-intensive initiatives, such as infrastructure upgrades or asset acquisitions, with full financial control and compliance. When you create an investment project in Project Operations, you automatically create a corresponding project in Microsoft Dynamics 365 Finance marked as an investment project.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Approvals|	5927453|	Expenses corrected via correction journal can't be submitted after recall.|
|Billing and Pricing|	5933042|	Discount on non-chargeable transactions is incorrectly calculated on total invoice amount.|
|Billing and Pricing|	6006562|	Block Updating Billing Type on Correction Invoices.|
|Project And Resource Management|	6017130|	Calendar rules aren't visible in calendar control after updating to Calendar V2.|
|Project And Resource Management|	6017133|	Project creation fails when calendar rule doesn't exist on a date.|
|Project And Resource Management|	6017865|	Import task fails to load the project when lookup column is added to the task entity.|
|Sales|	5748355|	Can't add new Project Contract line when inactive customer exists on that contract.|
|Sales|	5927010|	Transaction Category is blocked for updates on Quote Line Detail but not Contract Line Detail.|
|Sales|	6007632|	Audit history shows an error for Order Line when enabled on an environment.|
|Subcontracting|	4593261|	Canceled Vendor Invoices don't recreate inter-org actuals.|
|Subcontracting|	6039761|	TZA accounting date isn't initialized during automatic Vendor Invoice confirmation sync.|
|Time Entry|	6004629|	Delegate view for time entry entity is set as the default view.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1070810&dbType=3&qc=a80ae08ee0505a42d89c37cc39d4eb0486e58f41994329552d1063659d950495).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
