---
title: What's new April 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the April 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.date: 3/22/2024
ms.topic: article
ms.prod:
ms.reviewer: 
ms.author: mohitmenon
---

# What's new April 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.103.0.8.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.39.

## Project Operations dual-write maps updates

There are no Dual-write maps that are modified or added in the Project Operations April 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](https://github.com/MicrosoftDocs/dynamics-365-project-operations-pr/blob/PO_RN_UR39_Nov23/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](https://github.com/MicrosoftDocs/dynamics-365-project-operations-pr/blob/PO_RN_UR39_Nov23/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Increased task limit to 1000/project** <br><br> The new limit from Project for the Web scheduled projects in Project operations is 1000 tasks per project.| [Project and task limitations](../../project-management/project-and-task-limitations.md) |
| Project Management |**Editing Assignment Contours Phase 3** <br><br> In the assignments tab in the Project for the Web UI (the tasks tab on a project), users will now be able to view assignments in a monthly and yearly view (previously only daily and weekly views were available). Additionally, for tasks with no resource assigned, the unassigned contours will be visible (but read only until a resource is assigned).| [Editing resource assignment contours](../../project-management/create-assignments.md) |
| Project Management |**WBS Save Notification** <br><br> When changes are made in the WBS within Project for the Web, there is an asynchronous process to save those changes to Dataverse. Until the save to Dataverse is complete, some information in other tabs on the project (for example the estimates tab), may not reflect the changes. This feature will show an icon on the Project for the Web UI, which will indicate when a save is complete (green check mark) or ongoing (blue spinner).| [Saving changes to a project's WBS](../../project-management/saving-changes-to-projects.md) |
| Project Management |**Enable audit of Project Manager field** <br><br> The project manager, comments, status updated on, and scheduled start fields on the project entity were set to non-customizable to prevent customers from making changes which could negatively impact the product. However, this disabled the ability for customers to audit these fields. This feature allows those specific fields to be audited while keeping all other customizations disabled.| |
| Resource Management |**Intelligent multi-factor resource recommendations** <br><br> This is an extension to the Intelligent Resource Recommendations feature, which was initially released using only one factor (Experience Fit). Resources are now recommended using a combination of Experience Fit, Cost, Availability and Skill-match. Resources can also be compared, shortlisted and booked as a project team member.| [Prerequisites to use resource recommendations](../../resource-management/getting-started-with-resource-recommendations.md) <br><br> [Get intelligent resource recommendations](../../resource-management/get-recommendations-for-project-team-members.md) |
| Time Entry |**Copilot in Time Entry (preview)** <br><br> Copilot acts as your intelligent assistant and takes away some of the heavy lifting associated with logging work completed by you. Users will be able to create draft time entries from project assignments and generate editable external comments for all time entries using the Copilot sidecar experience. _(Only previewing for NAM Azure region)_.| (Documentation link to be updated) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3586943|	Estimate grid to show update to prices and Billing type (chargeability) when "Update prices" is selected.|
|Billing and Pricing|	3734257|	Use Transaction Date (Time zone independent) field instead of Document date during invoice creation. |
|Sales|	3749382|	Close As Won' fails if QuoteLineResourceCategory is pointing to Inactive ResourceCategory record.|
|Billing and Pricing|	3761980|	Recalculate API on invoice does not recalculate Chargeable amount, Non-chargeableamount etc.|
|Project Planning and Tracking|	3764826|	Copy Project has team members copied to the root business unit.|
|Approvals|	3801469|	Project approval billing type is only set with linked contract line.|
|Sales|	3815475|	Able to create/update estimate lines with invalid subcontract lines.|
|Billing and Pricing|	3817244|	Invoice with missing invoice lines are created when Project Contract has more than 5,000 contract lines (Project based lines + Product based lines).|
|Project Management|	3838992|	 Status reports displayed on the screen and as part of printed content are fully accessible.|
|Billing and Pricing|	3852034|	Billing hub does not reflect correct amount for "Fee" field, nor does it show the unbilled sales transactions of type" Fee" on clicking. |
|Project Contracts|	3859490|	Error with contract performance tab when contract is created without project.|
|Billing and Pricing|	3876272|	Invoice confirmation fails with error "An item with the same key has already been added."|
|Project Budgeting|	3884108|	During Revision Recreate Details for Expanded Budget Lines.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=886261).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
