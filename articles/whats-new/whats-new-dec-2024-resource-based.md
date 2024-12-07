---
title: What's new December 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the December 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 12/06/2024
ms.reviewer: johnmichalak

---

# What's new December 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.122.0.327.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.41.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations December 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Planning |**Enabling Enterprise Custom Columns (ETCC)** <br><br> Customers can now bring up to 10 custom columns on the task grid. These custom columns are read only. The supported formats are Text, Number, Date - Date only (not Date & time), Choice (but not yes/no fields)| |		
| Project Management |**Performance improvement in Schedule APIs for bulk operations** <br><br> As part of this feature, schedule APIs V2 now process multiple records at a time in a more efficient way that lead to over 75% improvement in performance.| |		

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Subcontracting|	3816001|	Validation added to ensure subcontract currency matches vendor currency.|
|Sales|	3819709|	Able to set or add a customer having a currency different than the contract (sales pricing).|
|Subcontracting|	3921055|	Actuals are generated with amount as zero on vendor invoices without unit price (despite a positive amount populated).|
|Project Estimates|	4152179|	Estimates OneGrid quick create form throws exception if a default unit/unit group doesn't exist.|
|Project Estimates|	4198360|	Estimate lines allow linking transaction categories that don't have an associated expense category.|
|Subcontracting|	4205520|	Actuals aren't generated when Manually Confirming a Vendor Invoice with AutoConfirm = True (integrated deployment).|
|Expense Management|	4220957| Correct validation that restricts Transaction Category ID to 28 characters (integrated deployment).|
|Time Entry|	4249478|	Project Operations license doesn't grant access to Team Member App.|
|Project Estimates|	4321523|	Project estimates not respecting effective date on price overrides.|
|Project Estimates|	4360880|	Project estimate updates feature breaks legacy estimates workflow customizations.|
|Sales|	4396988|	Fix **Project Contract is Missing** error thrown for nonadmin users when closing a quote as won. |
|Resource Management|	4413953| **An unexpected error occurred** or **Object reference not set to an instance of an object.** when trying to book a project resource from the schedule board without using team member generated requirement.|
|Billing and Pricing|	4424610|	Incorrect error message displayed when attempting to price a transaction that lacks a unit.|
|Subcontracting|	4435263|	PODW: Validation added to prevent vendor invoices from being auto confirmed without any vendor invoice lines.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=952752&dbType=3&qc=3b907b83fa0fe10ada99211e89737ca71d07b749a67c0a42302cca6fa39b1a5a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
