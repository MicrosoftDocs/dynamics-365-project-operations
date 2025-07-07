---
title: What's new November 2022 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the November 2022 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ryansandness
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ryansandness
---

# What's new November 2022 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.58.0.119
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.30

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Planning and Tracking | **Resource Assignment Contour Editing**<br> We are introducing the ability to edit the time phased effort of each resource assigned to a given task in the work breakdown structure, leveraging the modern Project for the Web project scheduling user interface. This new grid supports all of the existing experience in the Project for the Web including co-authoring and undo/redo.| [Editing Resource Assignment Contours](../project-management/create-assignments.md) |

## Quality updates

### Project Operations on Dataverse

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


### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).
