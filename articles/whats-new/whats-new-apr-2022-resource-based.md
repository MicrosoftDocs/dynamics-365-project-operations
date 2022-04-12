---
title: What's new April 2022 - Project Operations for resource/non-stocked based scenarios
description: This topic provides information about the quality updates that are available in the April 2022 release of Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 04/08/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new April 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This topic applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.41.0.45
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.26

## Features included in this release

**Procurement categories** can be used in **Project purchase orders** and pending vendor invoices. See more detail in [Use procurement categories with project purchase orders and pending vendor invoices](configure-procurement-categories.md)

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations March 2022 release.

| **Entity map** | **Updated version** | **Comments** |
| -------------- | ------------------- | --- ---------|
| Project Operations integration project vendor invoice line export entity msdyn\_projectvendorinvoicelines | 1.0.0.4 | Supporting procurement categories usage with purchase orders and pending vendor invoices|

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| ------------ | ---------------- | -------------- |
| Time and expense | 2573900 | Modern Approval feature must be enabled by default |
| Billing and pricing | 2603313 | Fixed duplicate record error preventing adding quote/ contract line with product |
| Deployment and configuration | 2611368 | Customer must be able to add up to 5 custom entities to the solution using modern app designer. |
| Time and expense | 2628285 | Fixed issue with setting correct resource category during time entry import |
| Opportunity management| 2628815 | Update Quote line detail description character limit to match task subject so import succeeds for tasks with subject longer than 100 characters |
| Time and expense| 2629547 | Submitted By field of Project Approvals must point to the user who submitted the record |
| Time and expense| 2629865 | Copy category field on tasks when copying projects |
| Time and expense| 2636463 | Fix filters on approvals in modern approvals forms|
| Project planning and tracking | 2648300 | Fixed issue preventing to change Project Owner|
| Billing and pricing | 2563000 | Journal line for unbilled sale with the currency different than the contract currency must not be allowed|

### Project management and accounting on Dynamics 365 Finance
For information about the bug fixes included in this update, sign in to Lifecycle Services (LCS) and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).
