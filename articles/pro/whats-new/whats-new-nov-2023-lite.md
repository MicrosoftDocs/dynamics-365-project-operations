---

title: What's new November 2023 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the November 2023 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: tulsijhaveri
---

# What's new November 2023 - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.88.0.127.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time entry | **In-grid editability within Modern Time Entry Grid** This new capability is available when users switch to the **Modern Time Entry Grid**. This release introduces in-grid editability of a project, project task, and role fields without using the **Edit Row** form. To edit in-drid, double-clicking these fields: for **Draft**, **Returned**, and **Recalled** rows. Subsequent releases have the ability to edit more fields. |   |
| Project Budget Management | **Sales budgets included in Project sales budget management.** Project Operations is expanding its budget management capabilities to include sales budgets. This means you can create, approve, revise, and track your sales budgets just like you do with cost budgets. Unbilled sales and billed sales actuals track against the sales budget lines. This expansion simplifies your experience by using the existing 'Enable Project Budgeting' feature flag. If you have already enabled 'Enable Project Budgeting' feature flag, you can create sales budgets along with cost budgets. In summary, Project Operations now offers unified and comprehensive budget management for both cost and sales, making it easier to manage your project budgets. | [Project budget management overview](../budget/projectbudgetmanagement.md) |
|Project Operations | **Project Operations Copilot**</br>This feature has been in Preview for NAM region and is now being released. The feature is on by default for US customers. Project management Copilot is an assistive capability that's powered by Microsoft Azure Open AI's large language model. The Copilot feature is designed to help improve the efficiency of different roles in Dynamics 365 Project Operations, including the project manager and practice manager. It provides a user-friendly and intuitive experience that helps maximize productivity while it also helps improve visibility into project performance. The Copilot feature has four capabilities: •	Task plan generation  •	Risk assessments •	Project status reports •	Interactive, chat-like experience| [Project management Copilot overview](/dynamics365/project-operations/project-management/copilot-features) |
| Project Management | **Project Calendar Control** Previously in the product, work hours could be set on a resource. Then that resource's work hours could be copied to create a calendar template. Then this calendar template could be applied to a project to create the project calendar. This was a bad experience and could lead to confusion because a copy was made each time not a link (both from resource to calendar template and calendar template to project). This was bad when the calendar template applied to a project was changed. Those changes wouldn't propagate to the project since the project looked at a copy of the calendar template's work hours. The new feature creates a calendar tab on the project entity, where the project's work hours can be viewed and edited directly, instead of dealing with the resource -\> calendar template -\> project process |
 


## Quality updates 

**Project Operations on Dataverse**

| **Feature area** | **Reference number** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3457165 | Invoice can be confirmed without Project Operations confirmation business logic. |
| Billing and Pricing | 3349847 | NRE in Project Operations integrated upon creating invoice with corrupted split billing rules. |
| Billing and Pricing | 3445951 | Actuals reevaluation fails for upgraded data - need split billing rule update. |
| Billing and Pricing | 3234349 | Journal Line can have contract line customer that doesn't match project contract. |
| Billing and Pricing | 3567544 | Quote Line Detail creation from Project Estimate Import failing. |
| Project Operations Upgrade | 3507354 | 3x add-in for Project Desktop can connect, read, and publish to an Upgraded PO4x org. |
| Project Planning and Tracking | 3572672 | Custom fields on tasks can't be updated via Dual-Write. |
