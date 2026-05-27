---
title: What's new May 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the May 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 05/27/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new May 2026 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:
- Project Operations in a Microsoft Dataverse environment version 4.167.3420.4.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.47.

## Project Operations dual-write map updates

The Project Operations May 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals |**Project Level Filtering for Approvals Agent** <br><br> The feature enables customers to decide which projects' approval records the agent should review. | |
| Project Planning |**Task Level Schedule Modes** <br><br> With task-level schedule modes, you can now override project scheduling mode on individual tasks to apply a different calculation behavior where needed. This capability gives project managers fine-grained control over scheduling without changing the project-wide setting.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	6244539|	Status Reason field can no longer be modified on confirmed invoices|
|Billing and Pricing|	6269908|	Modern Invoice - Form Contains Unsaved Changed When PendingTransactions Amount is $0|
|Billing and Pricing|	6299157|	PODW - Invoice view changes are missing from integrated org|
|Billing and Pricing|	6379494|	Modern Invoice - Pending transaction amount does not render|
|Journals|	6094351|	Time Zone Agnostic (TZA) Accounting Date is not being correctly defaulted|
|Billing and Pricing|	5727138|	Recalculate action on Quote comes up with a different cost price than from creating a Quote Line Detail|
|Billing and Pricing|	6031924|	Price is incorrectly set to $0 when recalculating Contract/Quote where no price record exists and time-phasing is enabled|
|Project And Resource Management|	6295665|	Team grid not loading automatically after project creation|
|Project Budgeting And Forecasting|	6232343|	Budget period setup is not creating the period for the selected month, instead creating one month before the end date|
|Project Budgeting And Forecasting|	6304128|	Project Budget - Import from estimates time phases the time budget lines incorrectly, with the wrong distribution|
|Project Estimates|	6111267|	Estimate line sales price is not re-defaulted after a cost price update|
|Project Estimates|	6293833|	Time phased estimates grid does not show correct currency when cost and sales currency don't match|
|Project Estimates|	6363037|	Cost Price for an estimate line should not be a required field on UI|
|Time Entry|	4662755|	Dark Mode Causes Visibility Issues in Time Entry Pages|
|Time Entry|	6020362|	Copy week causes screen flickering due to repeated backend calls|
|Project Planning And Tracking|	5860573|	Mismatch in the values between Required hours and Total Effort|
|Subcontracting|	6246178|	Aggregate Actuals does not happen for Actuals created after Vendor Invoice Auto Confirmation|

### Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1093817&dbType=3&qc=0ba12b7b2693bd9dd120bcfb9ea3707a649f62040e948aeb93691bdad057c79a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
