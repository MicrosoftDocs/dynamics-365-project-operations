---
title: What's new January 2023 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the January 2023 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new January 2023 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.59.0.210
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.30

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Planning and Tracking | **Importing Projects from Microsoft Project Desktop Client**<br>Project Operations allows Project Managers the ability to import their Project Desktop Files (.MPP) to create projects.| [Importing Projects from Microsoft Project Desktop Client](/dynamics365/project-operations/project-management/import_from_mpp) |
## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Time and Expense|2937019|Allow external comments field to editable while approving the time entry|
|Subcontracting|2966218|In Time Entry, the Subcontract field cannot be renamed|
|Project Planning and Tracking|3010541|Save plugin is not logging the correct error message in PSExceptionContent|
|Deployment and Configuration|3014550|PSCore deployment in CDS orgs is failing in URS related to xMultiple|
|Project Planning and Tracking|3029258|Import MPP for Project operations, BPF should not show up on Import form|
|Project Planning and Tracking|3029277|PSCore - Import/Copy passed but there was an error in PSS Error Logs: Unknown field: Target|
|Project Planning and Tracking|3029330|System job got canceled by a SQL deadlock|
|Project Planning and Tracking|3127468|Remote Link for "Send right status for each CDS request during save operation and remove redundant update of project status after operation is completed successfully"|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).
