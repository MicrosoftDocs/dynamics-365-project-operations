---
title: What's new November 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the November 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: TulsiJhaveri
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: TulsiJhaveri
---

# **What's new November 2023 - Project Operations Integrated with ERP**

**Applies To:**  Project Operations Integrated with ERP

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.88.0.127.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.37.

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the Project Operations November 2023 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration project vendor invoice export entity V2 (msdyn\_projectvendorinvoices) | 1.0.0.0 | New V2 entity added; This is required if user has enabled **Hold vendor payment** feature. The previous versioned entity, **Project Operations integration project vendor invoice export entity** , is deprecated and users should use the new updated entity.   |

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the  **Version**  column on the  **Dual-write**  page. To activate a new version of the map, select  **Table map versions** , select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release 

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Procurement | **Block vendor payments for vendor invoices until PM approval** </br>Facilitate the withholding of vendor payments for vendor invoices until they receive approval from the project manager in Dataverse. In some cases, project manager authorization is required before vendor payment can be initiated. In these cases, Accounts payable (AP) clerks document the invoice and wait for the project manager's approval before they process the payment. | [Block vendor payments until approved by a project manager](../pro/subcontracting/vi-blockvendorpaymentsforpmapproval.md) |
| Project Financials | **Enable Integration journal processing improvements** </br>This feature adds new functionality for the integration journal in Project Operations for resource/non-stock based deployments. With this feature enabled, new statuses are visible within the journal line in header to optimize posting to ensure work can be split up into multiple threads. Any journals encountering a posting error is prevented from posting again until the posting issue is addressed and the line is updated to draft status. | [Integration journal in Project Operations](../project-accounting/project-operations-integration-journal.md) |
| Time entry | **In-grid editability within Modern Time Entry Grid** </br>This new capability is available when users switch to the **Modern Time Entry Grid**. This release introduces in-grid editability of a project, project task, and role fields without using the **Edit Row** form. To edit in-drid, double-clicking these fields: for **Draft**, **Returned**, and **Recalled** rows. Subsequent releases have the ability to edit more fields. |   |
|Project Operations | **Project Operations Copilot**</br>This feature has been in Preview for NAM region and is now being released. The feature is on by default for US customers. Project management Copilot is an assistive capability that's powered by Microsoft Azure Open AI's large language model. The Copilot feature is designed to help improve the efficiency of different roles in Dynamics 365 Project Operations, including the project manager and practice manager. It provides a user-friendly and intuitive experience that helps maximize productivity while it also helps improve visibility into project performance. The Copilot feature has four capabilities: •	Task plan generation  •	Risk assessments •	Project status reports •	Interactive, chat-like experience| [Project management Copilot overview](/dynamics365/project-operations/project-management/copilot-features) |
| Project Management | **Project Calendar Control** Previously in the product, work hours could be set on a resource. Then that resource's work hours could be copied to create a calendar template. Then this calendar template could be applied to a project to create the project calendar. This was a bad experience and could lead to confusion because a copy was made each time not a link (both from resource to calendar template and calendar template to project). This was bad when the calendar template applied to a project was changed. Those changes wouldn't propagate to the project since the project looked at a copy of the calendar template's work hours. The new feature creates a calendar tab on the project entity, where the projects work hours can be viewed and edited directly, instead of dealing with the resource -\> calendar template -\> project process
 

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3457165 | Invoice can be confirmed without Project Operations confirmation business logic. |
| Billing and Pricing | 3349847 | NRE in Project Operations integrated upon creating invoice with corrupted split billing rules. |
| Billing and Pricing | 3445951 | Actuals reevaluation fails for upgraded data - need split billing rule update. |
| Billing and Pricing | 3234349 | Journal Line can have contract line customer that doesn't match project contract. |
| Billing and Pricing | 3567544 | Quote Line Detail creation from Project Estimate Import failing. |
| Project Operations Upgrade | 3507354 | 3x add-in for Project Desktop can connect, read, and publish to an Upgraded PO4x org. |
| Project Planning and Tracking | 3572672 | Custom fields on tasks can't be updated via dual-write. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=838613).
