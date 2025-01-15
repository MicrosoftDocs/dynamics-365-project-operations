---
title: What's new January 2025 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the January 2025 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 01/15/2025
ms.reviewer: johnmichalak

---

# What's new January 2025 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.123.0.X.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.42.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations January 2025 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budgeting |**Enable re-import of estimates/quote/contract on a revised budget version.** <br><br> As part of this enhancement, customers can reimport estimates onto a revised budget version which is in draft stage. To reimport the estimates, quote, or contract, revise the budget version and then reimport| [Create a project budget from estimates](../pro/budget/create-project-budget-from-estimates.md) |		

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Subcontracting|	3932178|	Auto matching failing for material vendor invoice lines|
|Subcontracting|	4205520|	Actuals are not generated when Manually Confirming a Vendor Invoice with AutoConfirm = True|
|Subcontracting|	4339657|	Unbilled sales actuals not found when chargeable task is added to contract line after vendor invoice is confirmed|
|Subcontracting|	4382804|	When closing quote as won, "Object reference not set to an instance of an object" error thrown|
|Billing and Pricing|	4403108|	Company with actuals linked to it can still be deleted |
|Billing and Pricing|	4473237|	Extended amount on retainer invoice lines get set to 0 after invoice recalculation|
|Time Entry|	4475300|	A previously "deactivated" bookable resource role can still be used within copy week functionality|
|Subcontracting|	4481246|	Actual Reevaluation: Vendor Invoice Cost Actuals Are Missing Fields|
|Sales|	4481592|	Product lines not showing correct tab when an invoice is created|
|Subcontracting|	4481635|	Actual Reevaluation: All Vendor Invoice Actuals Are Reversed When Task Deleted|
|Sales|	4486054|	Pressing recalculate on quote sets quote lines to 0 if there are no Quote Line Details|
|Project Estimates|	4486190|	"An item with the same key has already been added" appears when opening Time-phased Estimates tab|
|Resource Management|	4488867|	Adding team member directly in CDS for PSCore does not call PSS Create Team Member API|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=971730&dbType=3&qc=10e8ad5ad029bad3a0c2faa0e2dfc5d699a64ad8bfd2d1af37a5a02bb5800efa).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
