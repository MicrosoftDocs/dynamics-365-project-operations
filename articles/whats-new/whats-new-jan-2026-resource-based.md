---
title: What's new January 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the January 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 01/23/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new January 2026 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.162.0.228.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.46.

## Project Operations dual-write map updates

No updates for Project Operations dual-write maps in this release. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Stocked Products |**Enable stocked products usage for project operations integrated deployments** <br><br> This feature is an enhancement of the Stocked product usage in the Dynamics 365 Project operations integrated deployments. This feature allows you to reserve the inventory until Project Operations integration journal is posted in Dynamics 365 Finance for Project costs generated using Material usage or Journal. This process ensures that the inventory remains reserved and isn't consumed by other transactions such as sales orders, production orders, or material usage for other projects.| |
| Project Financials |**Enable beginning balances in Project Operations Integrated with ERP** <br><br> Beginning balances or opening balances, are transactions incurred outside Dynamics 365 Project Operations before you set up the project in the system. These balances typically arise in scenarios such as: Migrating from a legacy ERP system, maintaining financial records using other tools or manual processes. You can now move opening balances for projects, customers, and related financial data into Project Operations for continuity and accurate reporting. This process sets initial values for costs, revenue, work in progress (WIP), and billing.| |
| Time Entry |**Support for HH:MM Duration on New Time Entry form** <br><br> The New Time Entry form now comes with a new "Duration (HH:MM)" field that allows users to enter duration more flexibly. Any update to the "Duration" field automatically populates "Duration (HH:MM)" and vice versa.| |
| Project Management |**Outline number on assignments grid** <br><br> This enhancement displays task outline numbers in the assignment grid, enabling users to understand task hierarchy without navigating to the task grid| |
| Project Management |**Edit effort remaining on task grid** <br><br> Users can update remaining effort directly in the task grid, eliminating the need to navigate to the Tracking tab.| |
| Project Management |**Collapse or Expand all tasks** <br><br> Users can quickly expand or collapse all tasks in the task grid with one click.| |
| Project Budget Management |**Flexible project budget re‑import strategy** <br><br> This enhancement provides the flexibility to choose how source lines are merged with existing budget lines during project budget re‑import. User will have option to choose the re-import strategy between - Merge with Existing Lines, Reimport source lines (Preserving manual), Full reset (Remove all lines).| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Actuals|	5805457|	Project Tracking fields (totals) do not respect billing type of actuals|
|Approvals|	5786911|	Add validation to prevent creating Project Approvals with Null Entry Reference|
|Billing|	5766982|	Customers should not be allowed to delete confirmed invoices|
|Billing and Pricing|	4424625|	Relax Invoice Correction Validation to only consider Unit Group and not Units|
|Journals|	5761825|	Contract Customer does not default as expected on Journal Lines|
|Pricing|	5530159|	"Create custom pricing" doesn't work correctly with Role price markup|
|Project And Resource Management|	6017133|	Project creation fails when calendar rule doesn't exist on a date|
|Project And Resource Management|	6017865|	When a lookup column is added to the task entity, import task fails to load project|
|Project Budgeting And Forecasting|	5994590|	Skipped validation and defaulting for irrelevant Budget Line Attributes|
|Project Planning And Tracking|	4853288|	Newly added Time Zone Agnostic (TZA) fields were missing from the quick create forms within Project entity|
|Project Planning And Tracking|	5574797|	Copy Project operation should detect invalid project status and fail fast if the source project is invalid|
|Subcontracting|	4593261|	Canceled Vendor Invoices do not recreate inter-organisation actuals|
|Subcontracting|	5621818|	Unable to approve Material Usage with Stocked Products|
|Subcontracting|	5925197|	Error faced when revising a posted Project Invoice with select transactions|
|Time Entry|	5804612|	Users incorrectly get a warning message when submitting 8 Hours of Vacation/Absence on a working day|
|Time Entry|	5834568|	When end time of a Vacation type time entry exceeds working hours, the system incorrectly adds partial time off to the next working day|
|Time Entry|	5864012|	Open in Planner button opens the wrong URL for GCCH|
|Time Entry|	5884949|	Time Entry Calendar: Quick Create dialog fails to load on second open after creating an entry via Project search|
|Time Entry|	5916420|	Effort reprojection by updating Effort remaining is not working as expected|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1070810&dbType=3&qc=a80ae08ee0505a42d89c37cc39d4eb0486e58f41994329552d1063659d950495).
