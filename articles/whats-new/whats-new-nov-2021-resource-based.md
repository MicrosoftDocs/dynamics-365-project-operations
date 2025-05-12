---
title: What's new November 2021 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the November 2021 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new November 2021 - Project Operations for resource/non-stocked based scenarios

*Applies To: Project Operations for resource/non-stocked based scenarios*

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.26.0.145, 4.26.0.148, 4.26.0.150, 4.26.0.155
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.22

## Features included in this release

The following features are included in this release:

- Project Scheduling application programming interfaces (APIs) now support the ability to create and delete Project buckets.

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](/dynamics365/project-operations/environment/resource-dual-write-maps).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations in Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2240080 | The **Payment terms** field must not be duplicated on the pro forma invoice. |
| Billing and Pricing | 2358236 | Invoice correction must allow corrections that have zero-price lines. |
| Resource Management | 2410072 | Allow setup of a resource that is assigned to the task as a project manager. |
| Billing and Pricing | 2430234 | Fix a cost performance calculation issue. |
| Time and Expense | 2436978 | Allow time to be entered in hh:mm format. |
| Billing and Pricing | 2448623 | Allow price lists to be updated after they are associated with an organizational unit. |
| Time and Expense | 2460396 | Allow a time entry to be deleted by clearing the cell. |
| Billing and Pricing | 2467386 | Allow a project that has a task to be deleted, even when the task is associated with a won quote. |
| Time and Expense | 2461744 | The **My failed approval** view contains only project approvals in the **Submitted** stage. |
| Time and Expense | 2464082 | Remove the link from project approvals to the approval set when a target status is matched. |
| Time and Expense | 2468108 | The Schedule job should not set a **Processing** status for the approval set. |
| Time and Expense | 2471503 | Delete approval sets that are seven days old. |
| Billing and Pricing | 2480687 | The quote line reference must not be removed when a quote line milestone is created. |

### Project management and accounting in Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [584732](https://fix.lcs.dynamics.com/Issue/Details/?bugId=584732) | Retained vendor amounts in project expense transactions aren't shown in the transaction list. |
| Project management and accounting | [593068](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593068) | The intercompany vendor invoice is broken when vendor invoice integration is turned on. |
| Project management and accounting | [593382](https://fix.lcs.dynamics.com/Issue/Details/?bugId=593382) | The terms of payment on project invoices don't work as expected. |
| Project management and accounting | [596263](https://fix.lcs.dynamics.com/Issue/Details/?bugId=596263) | When vendor retention is released, the voucher posting has additional lines that are incorrect. |
| Project management and accounting | [598758](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598758) | When the Project Operations integration journal is posted, it fails because of missing dimensions for an account that isn't being posted to. |
| Project management and accounting | [602650](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602650) | The **Project** tab isn't editable on a pending vendor invoice when the procurement category is assigned to the item. |
| Project management and accounting | [605121](https://fix.lcs.dynamics.com/Issue/Details/?bugId=605121) | The navigation pane is missing if you aren't signed in to Project Operations Dataverse. |
| Project management and accounting | [602728](https://fix.lcs.dynamics.com/Issue/Details/?bugId=602728) | When you post revenue from a project invoice in an applied retainer case, an issue occurs because transactions on the voucher don't balance. |
| Project management and accounting | [603624](https://fix.lcs.dynamics.com/Issue/Details/?bugId=603624) | Creation of an estimate after you post an invoice proposal blocks correction lines from import. |
| Project management and accounting | [606083](https://fix.lcs.dynamics.com/Issue/Details/?bugId=606083) | Modification of a fully invoiced milestone record should not be possible. |
| Travel and Expense | [575305](https://fix.lcs.dynamics.com/Issue/Details/?bugId=575305) | All expense reports are visible when you search for a category in the Expense mobile app. |
| Travel and Expense | [583101](https://fix.lcs.dynamics.com/Issue/Details/?bugId=583101) | Incorrect amounts on vendor transactions and sales tax transactions are posted from an expense that is created from a credit card transaction. |
| Travel and Expense | [583760](https://fix.lcs.dynamics.com/Issue/Details/?bugId=583760) | An irrelevant warning occurs when you refresh the **Expense report** page. |
| Travel and Expense | [598656](https://fix.lcs.dynamics.com/Issue/Details/?bugId=598656) | The wrong interim approver is used when you delete an interim approver and then resubmit an expense report through the workflow. |
| Travel and Expense | [612742](https://fix.lcs.dynamics.com/Issue/Details/?bugId=612742) | A posting error that is related to mileage setup occurs. |
