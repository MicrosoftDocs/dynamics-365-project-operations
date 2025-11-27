---
title: What's new November 2025 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the October 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 11/27/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new November 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.161.0.36.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.45.

## Project Operations dual-write map updates

No updates for Project Operations dual-write maps in this release. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. Learn more in [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| Project Invoicing |**Billing Hub Phase 3** <br><br> 
The latest updates on Billing Hub addresses customer feedback for better visibility and control, reduces manual effort, and aligns with the long-term goal of making Billing Hub the central invoicing workspace. The updates can be accessed by enabling the flag 'Enable Billing Hub updates'. Key enhancements include: <br><br> 
- Visibility for “Not Ready to Invoice” transactions
- Streamlined Invoice Creation
- Instant Amount Calculations & Notifications
- Performance & UX Enhancements | |
| Approvals |**New Time Phased Approvals View** <br><br> The approvals view for time transactions is getting an overhaul to show information in a clearer and more concise format. Time approvals will be shown one week at a time, with transactions grouped together based on the columns added to the view in one row. PMs can then open a cell in that row to see more details for each day's entries and make edits as necessary.| |
| Project Management |**Customize Task Pane** <br><br> With this new feature enabled, clicking the "i" icon opens a customizable task pane that lets you manage tasks, customize them, and trigger business flows directly from the task grid context. You can still access the standard Project task pane via the overflow menu, giving you complete flexibility to choose between the custom Dataverse task pane and the Office task pane based on your requirements.| |
| Project Management |**Copy project new experience** <br><br> The new copy experience will allow Project Managets to copy projects by setting the right configurations for the project like Project name, Project manager, Calendar template, Schedule mode, Contracting unit, Currency and Team member options. The flow can also be customised as per your needs and copy projects to new or existing projects with no WBS.| |
| Project Management |**Copy externally scheduled projects** <br><br> The new copy experience brings along the copy project capability for an externally scheduled project. Now project managers can easily copy projects to new and existing projects with no WBS. This brings feature parity for externally scheduled projects.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Time Entry|	4583099|	Import From Resource Assignments is importing for incorrect days|
|Billing and Pricing|	5070121|	Unexpected error while updating applied advance amount an a confirmed invoice line |
|Project Planning|	5188687|	Start and Finish Date fields appear on forms even after being marked as hidden from maker portal|
|Subcontracting|	5344230|	Price Mismatch on Vendor Invoice Line Reconciliation|
|Subcontracting|	5346558|	Material estimate (line) does not copy the project task from the material estimate (line) onto the subcontract line that is created by 'subcontracting options'|
|Subcontracting|	5361570|	Defaulting for Unit and Unit Group is not working correctly for Subcontract Line|
|Time Entry|	5389918|	Vendor Field is not defaulted in Actual with subcontract and subcontract line|
|Subcontracting|	5534458|	Tax on the vendor invoice lines is incorrectly to unbilled sales actuals|
|Billing and Pricing|	5744336|	Preventing deletion of contract lines that have unbilled actuals|
|Subcontracting|	5769534|	Continue Booking button is disabled when all resources are shortlisted from Resource Recommendations|
|Project Planning|	5770199|	% Complete does not align with the EAC |
|Project And Resource Management|	5820499|	Resource assignment currency should match project currency to display estimates correctly|
|Project Budgeting And Forecasting|	5822655|	Month rollover issue during default project budget period creation|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1046049&dbType=3&qc=f7aa322e910d462ac082be99f72719f0d233f8a7a6973b89b8deb77f5d78fe98).
