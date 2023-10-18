---
title: What's new October 2023 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the October 2023 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.date: 10/17/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new October 2023 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.87.0.155.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.36.

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3509236|Contract Price List Update doesn't affect line details.|
|Billing and Pricing|3523321|Null reference exception in GetConvertedAmountForBusinessTransaction function.|
|Billing and Pricing|3568745|Fix price list prices delete plugin by using GetTargetEntityFromEntityReference.|
|Project Management|3514899|Revision token mismatch issue due to suppressed error causing transaction to be invalid.|
|Project Operations Upgrade|3546437|Error deleting task after upgrade if there's a customization on the relation between Task and Assignment.|
|Project Operations Upgrade|3551934|Orgs with Tasks and Assignments with no Project or Task linked in 3x should be blocked from upgrade to 4x and forced to clean up.|
|Project Operations Upgrade|3564488|Time out running PSA to PO upgrade data validation scripts.|
|Project Operations Upgrade|3589267|Create mitigation script to force fix affected relationships post 3x to 4x upgrade.|
|Time and Expense|3366683|Nonworking day pop-up displayed for time entries submitted on working days.|


### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=831854).
