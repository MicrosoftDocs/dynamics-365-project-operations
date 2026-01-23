---
title: What's new January 2026 - Project Operations Core
description: Learn about quality updates that are available in the January 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 01/23/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new January 2026 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.162.0.228.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Support for HH:MM Duration on New Time Entry form** <br><br> The New Time Entry form now comes with a new "Duration (HH:MM)" field that lets you enter a duration more flexibly. Any update to the "Duration" field automatically populates "Duration (HH:MM)" and vice versa.| |
| Project Management |**Outline number on assignments grid** <br><br> This enhancement displays task outline numbers in the assignment grid, enabling you to understand task hierarchy without navigating to the task grid| [Project task assignments](../../project-management/create-assignments.md#navigation) |
| Project Management |**Edit effort remaining on task grid** <br><br> You can update remaining effort directly in the task grid, eliminating the need to navigate to the Tracking tab.| [Project task assignments](../../project-management/create-assignments.md#navigation) |
| Project Management |**Collapse or Expand all tasks** <br><br> You can quickly expand or collapse all tasks in the task grid with one select.| [Working with project tasks](../../project-management/create-wbs.md#tasks) |
| Project Budget Management |**Flexible project budget re‑import strategy** <br><br> This enhancement provides the flexibility to choose how source lines are merged with existing budget lines during project budget re‑import. You have the option to choose the re-import strategy between - Merge with Existing Lines, Reimport source lines (Preserving manual), Full reset (Remove all lines).| [Summarize budget lines during import](../budget/summarize-budgetline-during-import.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference no.** | **Quality update** |
| --- | --- | --- |
|Actuals| 5805457| Project Tracking fields (totals) don't respect billing type of actuals.|
|Approvals| 5786911| Add validation to prevent creating Project Approvals with Null Entry Reference.|
|Billing| 5766982| Customers can't delete confirmed invoices.|
|Billing and Pricing| 4424625| Relax Invoice Correction Validation to only consider Unit Group and not Units.|
|Journals| 5761825| Contract Customer doesn't default as expected on Journal Lines.|
|Pricing| 5530159| "Create custom pricing" doesn't work correctly with Role price markup.|
|Project And Resource Management| 6017133| Project creation fails when calendar rule doesn't exist on a date.|
|Project And Resource Management| 6017865| When a lookup column is added to the task entity, import task fails to load project.|
|Project Budgeting And Forecasting| 5994590| Skipped validation and defaulting for irrelevant Budget Line Attributes.|
|Project Planning And Tracking| 4853288| Newly added Time Zone Agnostic (TZA) fields were missing from the quick create forms within Project entity.|
|Project Planning And Tracking| 5574797| Copy Project operation should detect invalid project status and fail fast if the source project is invalid.|
|Subcontracting| 4593261| Canceled Vendor Invoices don't recreate inter-organisation actuals.|
|Subcontracting| 5621818| Unable to approve Material Usage with Stocked Products.|
|Subcontracting| 5925197| Error faced when revising a posted Project Invoice with select transactions.|
|Time Entry| 5804612| You incorrectly get a warning message when submitting eight Hours of Vacation/Absence on a working day.|
|Time Entry| 5834568| When end time of a Vacation type time entry exceeds working hours, the system incorrectly adds partial time off to the next working day.|
|Time Entry| 5864012| Open in Planner button opens the wrong URL for GCCH.|
|Time Entry| 5884949| Time Entry Calendar: Quick Create dialog fails to load on second open after creating an entry via Project search.|
|Time Entry| 5916420| Effort reprojection by updating Effort remaining isn't working as expected.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
