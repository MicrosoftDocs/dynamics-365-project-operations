---
title: What's new June 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the June 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.date: 06/03/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new June 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.43.0.77
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.27

## Project Operations dual-write maps updates

The following list shows the dual-write maps that have been modified or added in the Project Operations June 2022 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration project vendor invoice export entity(msdyn_projectvendorinvoices) | 1.0.0.1 | Depreciated legacy field and mapped to the new field for vendor invoice state tracking |

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates
### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Subcontracting | 2708885 | Fixed error message thrown when user creates a bookable resource booking header record with no bookable resource filled in. |
| Project planning and tracking | 2629441 | Corrected workflow triggering logic to avoid infinte loop when updating project task.|
| Time and expense| 2641209 | Time Entries Import from Assignments/Bookings must retain Bookable Resource reference. |
| Project planning and tracking | 2651148 | Project Document Header must be guarded.  |
| Project planning and tracking | 2653145 | Added validations to ensure a project record cannot be created with invalid characters in it's name |
| Time and expense | 2654710 | Corrected filtering on Approvals form|
| Billing and pricing | 2667805 | Added validations to prevent creating billed sale actuals when backing unbilled sales actuals do not exist|
| Billing and pricing | 2668378 | Added validations to prevent adding custom pricing dimension without filling in logical name and field name |
| Subcontracting| 2677485 | Updated target version of vendor invoice lines dual write map|
| Time and expense | 2700428 | Improved approvals logic, ensuring other approval sets for the project can be processed, even if one of the approval sets is stuck in system jobs. |



### Project management and accounting in Dynamics 365 Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).
