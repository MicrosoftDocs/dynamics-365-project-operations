---
title: What's new October 2025 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the October 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 02/26/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new October 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.160.0.2877.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.45.

## Project Operations dual-write map updates

No updates for Project Operations dual-write maps in this release. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. Learn more in [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Import tasks from other projects** <br><br> You can now import tasks from one or multiple source projects to a new or existing target project. You can also import tasks into existing projects that have a work breakdown structure.| |		

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Actuals|	5145492|	Takes too long to load actions for a selected transaction (actual) record |
|Actuals|	5411195|	Unexpected ribbon button (Correct Entries) shows in Invoice Revision "Select Transactions" Form|
|Approvals|	4608553|	When task is chargeable and role is non-chargeable, billing type on the approval should be non-chargeable|
|Approvals|	5273101|	Validation added to prevent negative values for Billable Quantity on invoice|
|Approvals|	5561998|	Source document is not set on actuals that are created from adjusting Billable Quantity during approval|
|Approvals|	5574151|	Approvals Grid not showing more than 50 records and doesn't refresh when scrolled to the end to show more records|
|Billing|	5280983|	Billing Type can be edited on a Confirmed Invoice Line Detail|
|Project And Resource Management|	5545058|	Incorrect calculation of Effort Remaining|
|Project Planning And Tracking|	5290058|	Copy Project doesn't respect the resourcing company of original resources and stamps contracting company on all generic resources created|
|Sales|	5554329|	Default Contract or Quote currency from customer at the time of creation|
|Sales|	5562095|	Ready/Not Ready to Invoice ribbon buttons hidden for Product Based Contract Lines|
|Subcontracting|	5289777|	Incorrect pricing in QLD when Importing from estimates in intercompany scenario|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1046049&dbType=3&qc=f7aa322e910d462ac082be99f72719f0d233f8a7a6973b89b8deb77f5d78fe98).
