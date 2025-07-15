---
title: What's new November 2022 - Project Operations Core
description: This article provides information about the quality updates that are available in the November 2022 release of Microsoft Dynamics 365 Project Operations Core.
author: ryansandness
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ryansandness
---

# What's new November 2022 - Project Operations Core

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.58.0.119

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Deployment and Configuration | **Project Service Automation (PSA) to Project Operations  Core Upgrade Phase 2**<br>Phase 2 allows any PSA customer to upgrade their existing environments provided the projects in their work breakdown structures conform to the current limits supported by Project for the Web. | [Upgrade from Project Service Automation to Project Operations](../../psa/upgrade-project-operations-non-stocked.md) |
| Project Planning and Tracking | **Resource Assignment Contour Editing**<br> We are introducing the ability to edit the time phased effort of each resource assigned to a given task in the work breakdown structure, leveraging the modern Project for the Web project scheduling user interface. This new grid supports all of the existing experience in the Project for the Web including co-authoring and undo/redo.| [Editing Resource Assignment Contours](../../project-management/create-assignments.md) |
| Resource Management | **New Schedule Board for Universal Resource Scheduling (URS)**<br>The new and improved URS schedule board is now available for Project Operations.| [Experience the new and improved schedule board](/dynamics365/field-service/preview-schedule-board) |

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2781818 | Key not found error while defaulting price for material usage log. |
| Billing and Pricing | 2922373 | Can't link quote line to project that has closed as lost quote. |
| Billing and Pricing | 2943206 | **Contract Line** field in the Project Entity Should be Optional. |
| Billing and Pricing | 2953182 | Improve error message for correction invoices.|
| Billing and Pricing | 2959500 | Can't link quote line to a project task that is already associated with a lost quote.|
| Billing and Pricing | 2959560 | "This customer is already on the Project Contract" message received while closing quote as won in certain locales. |
| Billing and Pricing | 3031727 | Resource assignments fail with Required field 'msdyn_Company' is missing error. |
| Billing and Pricing | 3036905 | Owning Company is never initialized on the ProjectTeamMember. |
| Opportunity Management | 2763519 | Null Reference error in EnsureProjectContractAllowsUpdates. |
| Opportunity Management | 2783798 | When importing project estimates on quote line, task descriptions are missing for expense and material estimates.|
| Opportunity Management | 2988635 | Improve error msg description when deleting Customer on Quote. |
| Opportunity Management | 3001191 | Unable to create quote from Opportunity where billing method is specified as null. |
| Upgrade | 3012324 | Project conversion failed on a project with control characters like Tab in its name. |
| Project Planning and Tracking | 2790384 | The Pending OperationSet time-out is too short. |
| Project Planning and Tracking | 3044275 | Missing localization for: missingProjectSchedulerErrorMessage. |
| Project Planning and Tracking | 3044277 | Project Recon grid does not load when scheduler is unset.|
| Resource Management | 2943153 | Update Tracking tab to show two decimal places for Duration.|
| Subcontracting | 2932774 | Vendor Invoice Line Read Only throwing error incorrectly. |
| Subcontracting | 2939556 | Vendor Invoice Header status should not be set to Draft on line delete if not active. |
| Time and Expense | 2939998 | Uptake new TESA version in ProjOps. |
