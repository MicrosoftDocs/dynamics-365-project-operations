---
title: What's new May 2023 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the May 2023 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new May 2023 - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.72.0.123

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Resource Management| **Soft Bookings**</br>This enhancement allows you to create soft bookings on role based requirements. | |
|Project Planning and Tracking| **Task Labels**</br>This feature can help you quickly see what tasks have in common, such as requirements, locations, dependencies, or important time constraint. | [Use labels to sort tasks in Microsoft Project for the web](https://support.microsoft.com/en-us/office/use-labels-to-sort-tasks-in-microsoft-project-for-the-web-32dfc732-7bbc-48f0-9d17-672ddcd1905c). |
|Project Planning and Tracking| **Sprints**</br>This feature supports agile project management. You can create and prioritize a backlog of tasks and schedule tasks in sprints. You can also collaborate on planning, tracking, and completing tasks within, and across, time boxed sprints.| [Plan a project in sprints in Project for the web](https://support.microsoft.com/en-us/office/plan-a-project-in-sprints-in-project-for-the-web-7536fbef-0ece-47bf-beae-6a8ac2c69955). |
|Project Budgeting And Forecasting| **Improved budget match priority management**</br>In this new version, the budget match priority table has been updated to allow users to insert their own attributes. Prior to this release, the priority attributes were prioritized as 1, 2, 3, etc. The updated table now uses a priority sequence of 10, 20, 30, etc. The quick create forms have been modified to align with this new priority order. </br> </br>If any other attributes were added to the budget match priority table, they are overwritten and you need to recreate them. We apologize for any inconvenience this may cause.</br></br> We're currently working on resolving a known issue where the budget grid may not load or budget lines may not be visible. If you experience this issue, try refreshing your browser.| [Budget line match priority](/dynamics365/project-operations/pro/budget/budget-line-match-priority). |

## Quality updates
| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Project Planning and Tracking|3106933|Schedule API inconsistent handling of updates to Team Member name. |
|Project Planning and Tracking|3240017|ImportProject_Errors started failing due to new limit added on Project side. |
|Project Planning and Tracking|3324466|Add FCB for controlling using PCF Auth in PexWebControl in Dynamics solution. |
|Project Planning and Tracking|3335771|Disabled bookings cause early exit in PostProjectTeamMemberCreate and shared variable setting skipped. |
|Project Operations Upgrade|3242312|Fixed typo in data validation message - ProjectServiceValidateTaskAssignmentCount.cs. |
|Subcontracting|3300148|Error Dialog showing up on selecting Subcontract Line while creating Material Usage Log. |
