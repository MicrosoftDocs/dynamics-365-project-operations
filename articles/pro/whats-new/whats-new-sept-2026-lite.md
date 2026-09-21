---
title: What's new September 2026 - Project Operations Core
description: Learn about quality updates that are available in the September 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 09/21/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new September 2026 - Project Operations Core

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.171.3537.2.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry | **Use Outlook Meetings as a time entry source** <br><br> is a new configuration that enables team members to view Outlook meetings on the Time Entry Calendar interface and then use them to create time entries as well. | [Use Outlook as a time entry source](../../time/time-entry-configurations.md#use-outlook-meetings-as-a-time-entry-source) |
| Resource Management | **Configure Default Booking Methods** <br><br> Project Operations allows administrators to define default booking methods while using the Schedule Assistant or Schedule Board directly for booking resources. These defaults help standardize resourcing behavior across projects and reduce manual selection by project managers and resource managers. | [Configure booking methods in Project Operations](../../resource-management/booking-allocation-methods.md#configure-default-booking-methods) |
| Project Management | **Manage task grid column permissions** <br><br> Control column-level edit access in the task grid by configuring permissions at the organization, user, and project team member levels. Create permission templates and assign them across these levels to streamline administration and ensure consistent access management. | |
| Project Management | **Default task grid view** <br><br> You can now create and apply column configurations on the task grid which helps you to get a consistent view across the projects. Users still have option to alter the view per project basis. Apply these templates at organization level and per project level. You can also enforce the view settings to ensure users aren't allowed to alter the task grid view beyond allowed columns. | |
| Project Management | **Multiple Baselines** <br><br> Project Operations now supports 11 baselines, matching the Project Desktop experience. Capture multiple snapshots throughout the project lifecycle and compare them to understand how your project evolved over time. | |
| Project Management | **Task level calendars** <br><br> ask-level calendar support is now available in Project Operations. Assign different calendars to tasks, and the scheduling engine automatically uses them when calculating schedules, improving scheduling accuracy and reducing the need for off-system workarounds. | |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Actuals | 6293038 | Asynchronous processes can circumvent validations on actuals and lead to data corruption. |
| Approvals | 5927451 | Journal lines can be deleted in most scenarios. |
| Billing | 5989595 | Importing Invoice line transactions doesn't trigger recalculation on parent Invoice. |
| Billing | 6514403 | Posted correction invoice is missing tax information. |
| Billing | 6514537 | Correction invoice can't be posted if the tax is removed. |
| Billing | 6524553 | Retainers show up incorrectly on Billing Hub. |
| Billing | 6641322 | Invoice "Update totals" doesn't recalculate invoice line amounts - totals remain stale in new invoicing experience. |
| Pricing | 6247963 | Wrong price list picked up on save of Material Usage Log. |
| Pricing | 6256862 | Price List isn't stamped on Journal Line, price set to NULL. |
| Project And Resource Management | 6567653 | Inconsistent default values between new project and existing project when using Copy Project. |
| Resource Management | 6382335 | Stale SubcontractLine, WorkerType, and CostType on Resource Assignment after rebooking from contract worker to employee via Schedule Board. |
| Project Management | **Lookup and Currency Support for Custom Columns** <br><br> Add lookup and currency columns to the task grid to display related records and financial information directly within the grid, reducing the need for task form customizations. | |
| Journals | **New correction journal experience** <br><br> The new correction journals experience in Project Operations makes it easier to correct approved time, expense, and material transactions. You can combine different transaction types in a single journal, add entries to an existing draft, and apply different corrections to selected groups of entries through an editing side pane. Expanded correction options include quantities, billing type, and cost and sales prices, alongside project, task, resource, and transaction-specific fields. You can preview reversal and replacement journal lines before confirming, while entry-level correction status helps distinguish modified entries from unchanged entries. The new experience is initially optional, so organizations can continue using the existing correction journals experience until they enable it. | |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]