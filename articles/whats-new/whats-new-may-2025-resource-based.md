---
title: What's new May 2025 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the May 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new May 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.141.0.975.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.43.

## Project Operations Dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations May 2025 release.

For a current list and versions of Project Operations Dual-write maps, see [Project Operations Dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**New Time Entry Calendar View** <br><br> Team members can now interact with their time entries in a new calendar view. This view allows changing timelines to summarize time entries between Daily, Weekly, and Monthly horizons. In addition, the Time Entry Calendar comes with a Charts section that compares hours logged with target working hours and even allows users to filter time entries by status or type (Overtime, Vacation, etc.).| [New Time Entry Calendar (Preview)](../time/time-entry-calendar.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Approvals|	4606055|	Duplicate actuals generated for same time entry when actuals get reevaluated and approval gets canceled.|
|Approvals|	5060891|	External description is lost when submitting time, expense, material usage, or entry journal.|
|Billing and Pricing|	4769472|	Recurring Invoice Schedule - Duplicate Transactions when multiple records have the same Invoice Run Date.|
|Billing and Pricing|	4789534|	Can't Update Actuals Created By Dynamics 365 Field Service.|
|Billing and Pricing|	4789560|	Ensure Dual-write fields in actuals can only be updated via the Dual-write process.|
|Billing and Pricing|	4819057|	Payment Terms aren't being copied from split billing rules to customer invoice.|
|Billing and Pricing|	4826053|	Basis Price field values are inconsistent while copying from a source, only when the Cost Plus Pricing feature is enabled.|
|Billing and Pricing|	4840276|	Time phased estimate doesn't evaluate the right cost price when price overrides are used along with exchange rate.|
|Project and Resource Management|	4916438|	Show calendar tab by default for Project Operations users.|
|Sales|	4713365|	Quote or Contract Line Details of type "Time" shouldn't have units from different unit groups.|
|Sales|	4895890|	Unable to change invoicing status of progress based billing milestones using action buttons.|
|Sales|	4902277|	"The contract line can't be updated directly" error when trying to delete a project contract.|
|Sales|	5083058|	Chargeability on categories not honored while importing estimates.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=988112&dbType=3&qc=43dd064fcfe4d60f5434aafc5c6c738ffe2c57da200521808114fae9ff567a68).
