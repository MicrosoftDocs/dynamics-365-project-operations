---
title: What's new April 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the April 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 04/30/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new April 2026 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.166.3403.4.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.47.

## Project Operations dual-write map updates

There are no changes to dual-write maps in the Project Operations April 2026 release.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Calendar control has been updated from Version 1 to Version 2** <br><br> This update introduces a new calendar control with improved accessibility compliance. | |
| Project Management |**Team Member Grid Update** <br><br> The Team Member grid for projects has been updated to a more accessibility compliant grid with overall improved user experience. | |
| Team Member Experience |**Enhanced Team Member Experience (Preview)** <br><br> Users of the Project Operations Team Member app now get two new views (Assignments & Projects) to keep track of assigned tasks and Projects where they're staffed as members. The enhanced experience also allows team members to maintain private check-lists, notes and log time entries in a streamlined manner based on assigned work. | [Enhanced Team Member Experience in Project Operations](../time/enhanced-team-member-experience.md) |
| Time Entry |**Show and Hide Columns from the Modern Time Entry Grid (Early Access Feature)** <br><br> Users can now visibly hide or show columns from the Modern Time Entry Grid, without losing information from those columns while creating new in-line time entries. <br><br> **Note:** This feature of the Modern Grid is available in **early access** for 2 months, after which the **Modern Grid will be made the default time entry grid**. This change will take place in the **4.168.X.X version** of Project Operations. | [Show and Hide columns in Modern Grid](../time/modern-time-entry-grid.md#show-and-hide-columns-from-the-grid-without-losing-information) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	6225696|	Automated Invoice Creation batch job not working because the job is waiting forever|
|Billing and Pricing|	6226435|	Amount calculation discrepancy for Pending Transactions on the Modern Invoice form|
|Billing and Pricing|	6226438|	Invoice revision: Refunded retainer not showing up|
|Pricing|	5951126|	Opening a contract fails with an infinite loop error when Discount & Fee feature is enabled|
|Pricing|	6033981|	Inactive Price lists incorrectly get retrieved from Organizational Unit|
|Project And Resource Management|	6227343|	Importing fails for tasks from a project that has a billing setup|
|Project Estimates|	5820605|	Planned Sales displays amount in cost currency instead of converting from sales currency|
|Project Planning And Tracking|	6104736|	Unable to add column security on msdyn_actuallaborcost field|
|Resource Management|	5847284|	Partial Bookings made from "Hourly" view do not reflect on the Team Members grid|
|Sales|	5744203|	Billing type is not defaulting on update of role within Quote Line Details|
|Sales|	6092579|	Blocking creation of split billing rule for product lines to prevent invalid states|
|Sales|	6092582|	Allow deletion of split billing rules for product lines (currently blocked by error)|
|Sales|	6231254|	Incorrect Price Defaulting for Quotes at Recalculation|
|Subcontracting|	5973342|	Vendor Invoice Confirmation process updates Vendor Invoice status twice|
|Time Entry|	6120022|	Added validation to prevent changing project on time entries  that doesn't match with task via read only grid|


### Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1093817&dbType=3&qc=0ba12b7b2693bd9dd120bcfb9ea3707a649f62040e948aeb93691bdad057c79a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
