---
title: What's new April 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the April 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new April 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.62.0.83
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.32

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Management | **Cross Company Data Sharing**</br>Cross Company Data Sharing fills the gap between AX 2009, AX 2012, and Dynamics 365. Virtual company setup info sharing was possible in earlier versions but removed in Dynamics 365, causing upgrade issues. Now, Project Operations tables support virtual companies in Dynamics 365 as part of a global release. | [Tables supported for duplicate record data sharing](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-tables) |

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2904555|Block updates to Intercompany and Owning Company pricing dimensions.|
|Opportunity Management|3194606|Unable to Revise Quote with Write-in Material quote line details.|
|Project Operations Upgrade|3236820|The upgrade from version 3.x to 4.x is unsuccessful because of dependencies on other solutions.|
|Project Operations Upgrade|3264007|PSA to PO upgrade may fail on solution import at adding fields to ProductPriceLevel.|
|Project Planning and Tracking|3118566|PostProjectCreate plugin must check for Primary Requirement before Creating one.|
|Project Planning and Tracking|3258616|Copy project with one team member fails in Integrated Environment.|
|Subcontracting|3106796|Can attach Time-base subcontract line to Product-Based Order line.|
|Subcontracting|3196083|Material Subcontract Lines are not defaulting product unit & unit group as per subcontracting price list.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=787268).
