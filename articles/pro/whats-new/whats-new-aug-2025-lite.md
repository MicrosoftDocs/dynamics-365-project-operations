---
title: What's new August 2025 - Project Operations Core
description: This article provides information about quality updates that are available in the August release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 02/26/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new August 2025 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.143.0.3653.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management and Resource Management |**Add calendar control on calendar templates** <br><br> This feature activates the calendar control within the calendar template to allow you to update templates more easily and seamlessly.| [Define and edit project calendars](../../project-management/define-project-calendars.md) |
| Project Management and Resource Management |**Update task progress using schedule APIs** <br><br> We previously introduced a feature that allows you to update task progress directly from the task grid. This capability is now also available via schedule APIs, enabling you to modify the task's percentage complete using update APIs.| [Update the progress of a task](../../project-management/update-progress-of-a-task.md) |
| Project Management and Resource Management |**Import project experience** <br><br> The import project feature now allows you to select an existing project as the target for import. Additionally, you can configure more settings directly on the import screen before initiating the process.| |
| Project Budget Management |**Date flexibility in budget creation and actual matching** <br><br> This feature allows flexibility in handling actuals that fall outside the project’s start and end dates—such as pre and post-project contract activities, ensuring they can still be tracked against budget lines. Actuals that match all dimensions except for date are now flagged separately in budget line details, indicating alignment but falling outside the defined timeline.| [Project Budget Management Overview](../budget/projectbudgetmanagement.md)| 
| Time Entry | **Set Agent preferences from the Time Entry grid** <br><br> The time entry grid (both old and Modern) now come with a "Time Agent" section that lets you enable the Time Entry Agent and set preferences that were previously only supported within the Teams app. This change now makes the Teams app an optional part of the Time Agent setup experience.|  |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	4494831|	Revise Invoice doesn't update invoiced to date fields value.|
|Billing and Pricing|	4561292|	Divide by zero exception is thrown when conversion factor is zero while retrieving primary unit price.|
|Billing and Pricing|	5142586|	Billing type resets on form load for material type transaction class.|
|Billing and Pricing|	5272460|	NRE When Billed Sales Actual is Missing SplitBillingRule Fields.|
|Project Budgeting|	5209113|	Validate budget dates corresponding to project time zone agnostic dates.|
|Project Budgeting|	5248423|	Contract Customer should default invoice address to accounts primary address.|
|Sales|	4874297|	Error thrown when assigning same project to multiple quotes that are linked to the same opportunity.|
|Sales|	4926105|	Invoice schedule type not validated on quote line update.|
|Sales|	5166129|	Main form of the Quote Product line doesn't default to the Select Product to Existing.|
|Subcontracting|	5160260|	GetMaterialDefaults API fails during unit defaulting of Material Type Subcontract Lines|
|Subcontracting|	5226569|	Include adjustment value when correcting actual entries.|
|Time Entry|	4788137|	Duplicate Error message when user tries to edit multiple submitted/approved time entries.|
|Time Entry|	4864943|	Calendar Rules get moved after approval due to time zone differences between manager and team member.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
