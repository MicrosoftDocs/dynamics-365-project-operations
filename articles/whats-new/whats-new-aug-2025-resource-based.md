---
title: What's new August 2025 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the August 2025 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
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

# What's new August 2025 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.143.0.3653.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.44.

## Project Operations Dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Sales |**Manage multiple addresses for accounts** <br><br> This feature enables the management of multiple physical addresses for customers, vendors, and contacts. It also supports the use of delivery addresses in project quotations, contracts, and invoices.| [Manage and apply multiple account addresses to project invoices](../pro/sales/manage-global-address-book.md) |
| Project Management and Resource Management |**Add calendar control on calendar templates** <br><br> This feature activates the calendar control within the calendar template, allowing you to update templates more easily and seamlessly.| [Define and edit project calendars](../project-management/define-project-calendars.md) |
| Project Management and Resource Management |**Update task progress using schedule APIs** <br><br> We previously introduced a feature that allows you to update task progress directly from the task grid. This capability is now also available via schedule APIs, enabling you to modify the task's % complete using update APIs| [Update the progress of a task](../project-management/update-progress-of-a-task.md) |
| Project Management and Resource Management |**Import project experience** <br><br> The import project feature now allows you to select an existing project as the target for import. Additionally, you can configure more settings directly on the import screen before initiating the process.| |
| Project Budget Management |**Date flexibility in budget creation and actual matching** <br><br> This feature allows flexibility in handling actuals that fall outside the project’s start and end dates—such as pre and post-project contract activities, ensuring they can still be tracked against budget lines. Actuals that match all dimensions except for date are now flagged separately in budget line details, indicating alignment but falling outside the defined timeline.| [Project Budget Management Overview](../pro/budget/projectbudgetmanagement.md)| 
| Time Entry | **Set Agent preferences from the Time Entry grid** <br><br> The time entry grid (both old and Modern) now come with a "Time Agent" section that lets you enable the Time Entry Agent and set preferences that were previously only supported within the Teams app. This change now makes the Teams app an optional part of the Time Agent setup experience.|  |


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	4494831|	Revise Invoice doesn't update invoiced to date fields value.|
|Billing and Pricing|	4561292|	Divide by zero exception is thrown when conversion factor is zero while retrieving primary unit price.|
|Billing and Pricing|	5054918|	Applied retainers incorrectly applied against finance and operations tax.|
|Billing and Pricing|	5142586|	Billing type resets on form load for material type transaction class.|
|Billing and Pricing|	5272460|	NRE When Billed Sales Actual is Missing SplitBillingRule Fields.|
|Project and Resource Management|	5001281|	Unable to mark task as completed on integrated org.|
|Project Budgeting|	5209113|	Validate budget dates corresponding to project time zone agnostic dates.|
|Project Budgeting|	5248423|	Contract Customer should default invoice address to accounts primary address.|
|Sales|	4874297|	Error thrown when assigning same project to multiple quotes that are linked to the same opportunity.|
|Sales|	4926105|	Invoice schedule type not validated on quote line update.|
|Sales|	5166129|	Main form of the Quote Product line doesn't default to the Select Product to Existing.|
|Subcontracting|	5160260|	GetMaterialDefaults API fails during unit defaulting of Material Type Subcontract Lines.|
|Subcontracting|	5169095|	Vendor Invoice Creation Fails Due to Transaction Classification Mismatch on Subcontract Line.|
|Subcontracting|	5226569|	Include adjustment value when correcting actual entries.|
|Time Entry|	4788137|	Duplicate Error message when user tries to edit multiple submitted/approved time entries.|
|Time Entry|	4864943|	Calendar Rules get moved after approval due to time zone differences between manager and team member.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1028749&dbType=3&qc=ce23ba904cf7dc2e2233a5d951b6a5974c350ed77aded0cd55f33a94a7cd6d84).
