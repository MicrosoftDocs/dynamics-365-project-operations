---
title: What's new January 2023 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the January 2023 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new January 2023 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.59.0.210

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Planning and Tracking | **Importing Projects from Microsoft Project Desktop Client**<br>Project Operations allows Project Managers the ability to import their Project Desktop Files (.MPP) to create projects.| [Importing Projects from Microsoft Project Desktop Client](/dynamics365/project-operations/project-management/import_from_mpp) |
| Project Budgeting and Forecasting | **Project cost budget management – Manual**<br>Introducing first phase of project budget management in Project Operations Lite deployment. This is the first step towards providing budget management in Project Operations Lite deployment. <br> Capabilities included in this release – Manual project cost budget creation; Approval & rejection of budget; Actual to budget line matching for time, expense, material actuals.|[Project cost budget management](/dynamics365/project-operations/pro/budget/projectbudgetmanagement)|


## Quality updates
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
