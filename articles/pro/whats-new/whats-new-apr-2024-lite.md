---
title: What's new April 2024 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the April 2024 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: mohitmenon
ms.date: 04/09/2024
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new April 2024 - Project Operations Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core._

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.103.0.8.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Increased task limit to 1,000 per project** <br><br> The new limit from Project for the web scheduled projects in Project Operations is 1,000 tasks per project.| [Project and task limitations](../../project-management/project-and-task-limitations.md) |
| Project Management |**Editing Assignment Contours Phase 3** <br><br> Users can now view assignments in a monthly and yearly view, under the tasks tab of a project. Additionally, for tasks without resources assigned, the unassigned contours are visible but in read-only state until a resource is assigned. These changes are available post March via Project for the web.| [Editing resource assignment contours](../../project-management/create-assignments.md) |
| Project Management |**Work Breakdown Structure (WBS) Save Notification** <br><br> When changes are made in the work breakdown structure within Project for the web, there's an asynchronous process to save those changes to Dataverse. Until the save to Dataverse is complete, some information in other tabs on the project (for example the estimates tab), may not reflect the changes. This feature shows an icon on the Project for the web UI that indicates when a save is complete (green check mark) or on-going (blue spinner).| [Saving changes to a project's WBS](../../project-management/saving-changes-to-projects.md) |
| Project Management |**Enable audit of Project Manager field** <br><br> Fields like **Project manager**, **Comments**, **Status updated on**, and **Scheduled start**, on the Project entity were set to noncustomizable to prevent customers from making changes that could negatively impact the product. However, this also disabled customers' ability to audit these fields. This feature allows those specific fields to be audited while keeping all other customizations disabled.| |
| Resource Management |**Intelligent multi-factor resource recommendations** <br><br> This is an extension to the Intelligent Resource Recommendations feature, which was initially released using only one factor (Experience Fit). Resources are now recommended using a combination of Experience Fit, Cost, Availability, and Skill-match. Resources can also be compared, shortlisted, and booked as a project team member.| [Prerequisites to use resource recommendations](../../resource-management/getting-started-with-resource-recommendations.md) <br><br> [Get intelligent resource recommendations](../../resource-management/get-recommendations-for-project-team-members.md) |
| Time Entry |**Copilot in Time Entry (preview)** <br><br> Copilot acts as your intelligent assistant and takes away some of the heavy lifting associated with logging work completed by you. Users are able to create draft time entries from project assignments and generate editable external comments for all time entries using the Copilot sidecar experience. _(Only previewing for NAM Azure region)_.|  |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3586943|	Estimate grid to show update to prices and Billing type (chargeability) when "Update prices" is selected.|
|Billing and Pricing|	3734257|	Use Transaction Date (Time zone independent) field instead of Document date during invoice creation. |
|Sales|	3749382|	Close As Won fails if QuoteLineResourceCategory is pointing to Inactive ResourceCategory record.|
|Billing and Pricing|	3761980|	Recalculate API on invoice doesn't recalculate the Chargeable amount, Nonchargeable amount, etc.|
|Project Planning and Tracking|	3764826|	Copy Project has team members copied to the root business unit.|
|Approvals|	3801469|	Project approval billing type is only set with linked contract line.|
|Sales|	3815475|	Able to create and update estimate lines with invalid subcontract lines.|
|Billing and Pricing|	3817244|	Invoice with missing invoice lines is created when Project Contract has more than 5,000 contract lines (Project based lines + Product based lines).|
|Project Management|	3838992|	 Status reports displayed on the screen and as part of printed content are fully accessible.|
|Billing and Pricing|	3852034|	Billing hub doesn't reflect correct amount for the **Fee** field, nor does it show the unbilled sales transactions of type **Fee** when selected. |
|Project Contracts|	3859490|	Error with contract performance tab when contract is created without project.|
|Billing and Pricing|	3876272|	Invoice confirmation fails with error **An item with the same key is already added**.|
|Project Budgeting|	3884108|	During Revision Recreate Details for Expanded Budget Lines.|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
