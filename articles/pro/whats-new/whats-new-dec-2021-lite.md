---
title: What's new December 2021 - Project Operations lite deployment
description: This topic provides information about the quality updates that are available in the December 2021 release of Project Operations lite deployment.
author: sigitac
ms.date: 12/09/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new December 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.27.0.195


## Features included in this release

- Improved troubleshooting for system administrators. When a user can't open a project, the administrator can review non-license related errors generated from Project for the web in [Project scheduling logs](../../project-management/schedule-api-logs.md).
- [Use task checklists in Microsoft Project for the web](https://support.microsoft.com/en-us/office/use-task-checklists-in-microsoft-project-for-the-web-c69bcf73-5c75-4ad3-9893-6d6f92360e9c). In Microsoft Project for the web, you can add a checklist to a task to keep track of specific items.

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Planning and Tracking | 2392596 | Schedule APIs now allow updates to the **Effort remaining**, **Effort completed**, and **% Complete** fields. |
| Planning and Tracking | 2478497 | Schedule APIs **Activity number** and **Task ID** fields can be blank on input because the system will populate them using automated numbering.|
| Time and Expense | 2468135 | The number of approval retries is reduced from five to three. |
| Time and Expense | 2468188 | Fixed the issue with log text exceeding the maximum length in the **notetext** attribute of the **annotation** entity. |
