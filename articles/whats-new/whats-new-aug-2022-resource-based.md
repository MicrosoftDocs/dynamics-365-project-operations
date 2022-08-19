---
title: What's new August 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the August 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.date: 07/19/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new August 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.45.0.53
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.28

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the August 2022 release of Project Operations.

| Entity map | Updated version | Comments |
| -------------- | ------------------- | ------------|
| Project Operations integration actuals (msdyn\_actuals) | 1.0.0.15 | TBD |
| Project Operations integration project vendor invoice export entity (msdyn\_projectvendorinvoices) | 1.0.0.2 | TBD |
| Project Operations integration project vendor invoice line export entity (msdyn\_projectvendorinvoicelines) | 1.0.0.5 | TBD |

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Opportunity management | 2762089 | Error handling while closing the contract as lost if auto-save is disabled in the org.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).
