---
title: What's new December 2023 - Project Operations Core
description: This article provides information about the quality updates that are available in the December 2023 release of Microsoft Dynamics 365 Project Operations Core.
author: tulsijhaveri
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.reviewer: johnmichalak 
ms.author: tulsijhaveri
---

# What's new December 2023 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.89.0.15.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budget Management | **Summarization of cost and sales budget lines during import to budget** This feature enables you to import estimates that are initially detailed but are then presented as summarized budget lines. This feature streamlines project tracking by reducing the number of budget lines. The summarization process adheres to the budget match priority, ensuring consistency even when selecting summarization options during import. | [Project budget management overview](/dynamics365/project-operations/pro/budget/projectbudgetmanagement) |
| Proforma Invoicing | **Ability to select and revise specific transactions in an invoice.** This feature improves usability and performance of the invoice correction process. Users can select a subset of the transactions for correction without needing to revise the entire invoice, which leads to efficient and shorter invoicing cycles. | [Revise (correct) project invoices](../../proforma-invoicing/revise-project-invoices.md) |

## Quality updates

**Project Operations on Dataverse**

| **Feature area** | **Reference number** | **Quality Update** |
| --- | --- | --- |
| Project Planning and Tracking | 3655580 | Unsaved alert shows on project form when feature is disabled and duration fields are hidden. |
| Project Planning and Tracking | 3647289 | Create error log when user doesn't have permissions to async operation entity and can't query the system jobs. |
| Project Planning and Tracking | 3662968 | Create error log when user is missing any OOB privilege and save operation fails. |
| Project Planning and Tracking | 3647295 | Create PSS Error log when the convert project fails. |
| Project Planning and Tracking | 3349866 | Project app user is missing readAccount privilege. |
| Project Planning and Tracking | 3615118 | Project is stuck in Copying/Importing/Converting status if PSS failed to update project status to Failed due to permission issue. |
| Project Planning and Tracking | 3648246 | Plugin Deprecated: Microsoft.Dynamics.ProjectServiceCoreSandbox.Plugins.Plugins.PublishToEventHub.PostOperationUserUpdateEvent |
