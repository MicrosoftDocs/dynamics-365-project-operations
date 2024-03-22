---
title: What's new April 2024 - Project Operations Lite deployment
description: This article provides information about the quality updates that are available in the April 2024 release of Microsoft Dynamics 365 Project Operations Lite deployment.
author: mohitmenon
ms.date: 3/22/2024
ms.topic: article
ms.prod:
ms.reviewer: 
ms.author: mohitmenon
---

# What's new April 2024 - Project Operations Lite deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.103.0.8.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Increased task limit to 1000/project** <br><br> The new limit from Project for the Web scheduled projects in Project operations is 1000 tasks per project.| [Project and task limitations](../../project-management/project-and-task-limitations.md) |
| Project Management |**Editing Assignment Contours Phase 3** <br><br> In the assignments tab in the Project for the Web UI (the tasks tab on a project), users will now be able to view assignments in a monthly and yearly view (previously only daily and weekly views were available). Additionally, for tasks with no resource assigned, the unassigned contours will be visible (but read only until a resource is assigned).| [Editing resource assignment contours](../../project-management/create-assignments.md) |
| Project Management |**WBS Save Notification** <br><br> When changes are made in the WBS within Project for the Web, there is an asynchronous process to save those changes to Dataverse. Until the save to Dataverse is complete, some information in other tabs on the project (for example the estimates tab), may not reflect the changes. This feature will show an icon on the Project for the Web UI, which will indicate when a save is complete (green check mark) or ongoing (blue spinner).| |
| Project Management |**Enable audit of Project Manager field** <br><br> The project manager, comments, status updated on, and scheduled start fields on the project entity were set to non-customizable to prevent customers from making changes which could negatively impact the product. However, this disabled the ability for customers to audit these fields. This feature allows those specific fields to be audited while keeping all other customizations disabled.| |
| Resource Management |**Intelligent multi-factor resource recommendations** <br><br> This is an extension to the Intelligent Resource Recommendations feature, which was initially released using only one factor (Experience Fit). Resources are now recommended using a combination of Experience Fit, Cost, Availability and Skill-match. Resources can also be compared, shortlisted and booked as a project team member.| |
| Time Entry |**Copilot in Time Entry (preview)** <br><br> Copilot acts as your intelligent assistant and takes away some of the heavy lifting associated with logging work completed by you. Users will be able to create draft time entries from project assignments and generate editable external comments for all time entries using the Copilot sidecar experience. (Only previewing for NAM Azure region).| |
