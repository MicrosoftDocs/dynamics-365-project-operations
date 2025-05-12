---
title: What's new May 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the May 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new May 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.42.0.70
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.26

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates
### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Resource management | 2634019 | Improved error messages for business validations when adding generic team members as resources. |
| Project planning and tracking | 2648515 | Restricted updates of **ownerid**, **state**, and **status** in scheduling entities. |
| Billing and pricing | 2653167 | The **Estimates** grid decimal separator must follow format settings in **Personal Options**. |
| Billing and pricing| 2662251 | Values in the **Corrected unit** and **Unit group** fields default when creating records in material estimates. |
| Billing and pricing| 2571408 | Unbilled sales actuals are stamped with a proforma invoice ID when creating a draft invoice. |

### Project management and accounting in Dynamics 365 Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).
