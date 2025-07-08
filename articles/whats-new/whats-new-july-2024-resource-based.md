---
title: What's new July 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the July 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new July 2024 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.106.0.3.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40.

## Project Operations dual-write maps updates

_There are no Dual-write maps that are modified or added in the Project Operations July 2024 release._

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release
No new features are included in this release for the Core deployment.


## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing | 3788836 | Invoice revision fails for manually created ILDs on TM Invoice Lines without a project reference.|
|Billing and Pricing | 3844999 | Currency Validation for Role Prices on Cost Price Lists.|
|Sales|	3853801| Quote line detail and contract line detail DW pre create validation should default owning company instead of throwing an exception.|
|Time Entry| 4103100 | Modern Time Entry Grid - Now adheres to the "Start day of week" set as per system settings.|
|Billing and Pricing| 4124103 | Prevent recall of approved time entries that are already billed to a (confirmed) invoice.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=936136&dbType=3&qc=4bfbc812bab8c497f0747156b4e6faa90d7d73b55226bc7406f2a9b71839162e).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
