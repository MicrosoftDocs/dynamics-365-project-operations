---
title: What's new August 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the Aug 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 08/23/2024
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new August 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.108.0.15.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations August 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

No new features for this release of Project Operations for resource/non-stocked based scenarios.


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3546798|	A scope with nonmatching currency can be added to price overrides.|
|Project Planning and Tracking|	3742761| Add work hour template to the list of restricted attributes when copying data from source project.|
|Billing and Pricing|	3802977|	Hide the **Price Override** button for cost record.|
|Billing and Pricing|	3883056|	Rounding precision isn't being honored with primary unit creating incorrect actuals.|
|Project Budget Management|	3929679|	In Draft mode of budget grid, Task field is showing tasks of ALL project not just the current project.|
|Billing and Pricing|	3941977|	Can't deactivate a price list with overrides.|
|Sales|	3981724|	Duplicate contract split billing rules can be created.|
|Sales|	4161956|	Syncing from sales to cost when updating Quote Line Details prevents the update of totals on the QL.|
|Billing and Pricing|	4173215|	Don't allow deleting contract lines that have unbilled invoice lines.|
|Subcontracting|	4181897|	The default expense category is on the expense quick create form when subcon and subcon line fields are selected.|
|Time Entry|	4186684|	Time Off entry doesn't get cleared from resource calendar when time entry type is changed to Work or Overtime.|
|Billing and Pricing|	4192197|	Negative actuals don't have replacing Unbilled Sales actuals created on correction invoice confirmation.|
|Billing and Pricing|	4199581|	Script error occurs when clicking on Invoiceable backlog in Billing hub.|
|Billing and Pricing|	4211979|	Invoice Line Detail (ILD) correction field can be true even when original ILD is blank.|
|Billing and Pricing|	4212681|	Can have applied retainer on invoice after retainer is refunded.|
|Project Budget Management|	4229374|	Group by isn't working in project budget line subgrid.|
|Time Entry|	4231555|	Fix entity name regression that caused issues with time entry deletion and workflow modification.|
|Sales|	4300829|	Move PBB Confirm Logic Causes Invoice Confirmation Failure > 5000 ILDs.|


### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=936136&dbType=3&qc=4bfbc812bab8c497f0747156b4e6faa90d7d73b55226bc7406f2a9b71839162e).

[!INCLUDE[footer-include](../includes/footer-banner.md)]


