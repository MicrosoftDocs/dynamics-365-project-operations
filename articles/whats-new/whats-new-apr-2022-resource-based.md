---
title: What's new April 2022 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the April 2022 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new April 2022 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.41.0.45
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.26

## Features included in this release

Procurement categories can be used in project purchase orders and pending vendor invoices. For more information, see [Use procurement categories with project purchase orders and pending vendor invoices](../procurement/configure-procurement-categories.md).

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the March 2022 release of Project Operations.

| Entity map | Updated version | Comments |
| -------------- | ------------------- | ------------|
| Project Operations integration project vendor invoice line export entity msdyn\_projectvendorinvoicelines | 1.0.0.4 | This map supports the use of procurement categories with purchase orders and pending vendor invoices. |

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| ------------ | ---------------- | -------------- |
| Time and expense | 2573900 | The **Modern Approval** feature must be enabled by default. |
| Billing and pricing | 2603313 | Fixed a duplicate record error that prevented quote and contract lines that have a product from being added. |
| Deployment and configuration | 2611368 | Customers must be able to add up to five custom entities to the solution by using the modern app designer. |
| Time and expense | 2628285 | Fixed an issue that affected the ability to set the correct resource category during time entry import. |
| Opportunity management| 2628815 | Update the character limit of the quote line detail description to match the character limit of the task subject, so that import succeeds for tasks where the subject is longer than 100 characters. |
| Time and expense| 2629547 | The **Submitted By** field of project approvals must point to the user who submitted the record. |
| Time and expense| 2629865 | The **Copy category** field on tasks when projects are copied. |
| Time and expense| 2636463 | Fixed the filters on approvals in modern approvals forms. |
| Project planning and tracking | 2648300 | Fixed an issue that prevents the project owner from being changed. |
| Billing and pricing | 2563000 | Journal lines for an unbilled sale where the currency differs from the contract currency must not be allowed. |

### Project management and accounting in Dynamics 365 Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).
