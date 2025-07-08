---
title: What's new May 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the May 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new May 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.72.0.123
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.33

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Revenue Recognition | **Enable contract line based revenue recognition with Project Operations for non-stocked/ resource based scenarios**</br>This feature allows you to generate revenue recognition for a contract line. When there are multiple contract lines for a contract, multiple revenue recognition projects can be created for each contract line and revenue recognition can be calculated differently.| [Contract line-based revenue recognition with Project operations](/dynamics365/project-operations/revenue-recognition/revenuerecogntionforcontractlines) |
|Resource Management | **Soft Bookings**</br>This enhancement allows you to create soft bookings on role based requirements.| |
|Project Planning and Tracking | **Task Labels**</br>This feature can help you quickly see what tasks have in common, such as requirements, locations, dependencies, or important time constraint. | [Use labels to sort tasks in Microsoft Project for the web](https://support.microsoft.com/en-us/office/use-labels-to-sort-tasks-in-microsoft-project-for-the-web-32dfc732-7bbc-48f0-9d17-672ddcd1905c).  |
|Project Planning and Tracking| **Sprints**</br>This feature supports agile project management. You can create and prioritize a backlog of tasks and schedule tasks in sprints. You can also collaborate on planning, tracking, and completing tasks within, and across, time boxed sprints.| [Plan a project in sprints in Project for the web](https://support.microsoft.com/en-us/office/plan-a-project-in-sprints-in-project-for-the-web-7536fbef-0ece-47bf-beae-6a8ac2c69955). |

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Project Planning and Tracking|3106933|Schedule API inconsistent handling of updates to Team Member name.|
|Project Planning and Tracking|3240017|ImportProject_Errors started failing due to new limit added on Project side.|
|Project Planning and Tracking|3324466|Add FCB for controlling using PCF Auth in PexWebControl in Dynamics solution. |
|Project Planning and Tracking|3335771|Disabled bookings cause early exit in PostProjectTeamMemberCreate and shared variable setting skipped.|
|Project Operations Upgrade|3242312|Fixed typo in data validation message - ProjectServiceValidateTaskAssignmentCount.cs.|
|Subcontracting|3300148|Error Dialog showing up on selecting Subcontract Line while creating Material Usage Log.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=795940).
