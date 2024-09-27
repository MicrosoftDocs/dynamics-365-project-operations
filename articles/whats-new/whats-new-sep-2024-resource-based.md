---
title: What's new September 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the Sep 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.topic: conceptual
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 09/27/2024
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new September 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.120.0.19.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.41.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations September 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Billing & Pricing |**Discounts and Fee** <br><br> Define discount and fee percentages at the project quote or contract line level. When a transaction is generated and approved, the system applies the appropriate discount or fee based on the contract line setup and updates the actuals accordingly. This feature is applicable to Time and Material business processes.| |
| Billing & Pricing |**Role price override within Quote Line Detail form** <br><br> The Price Override button, integrated into the Quote Line form, facilitates the modification of price overrides for quote line details. This functionality significantly reduces the number of clicks and streamlines the process of adjusting prices while maintaining focus within the context of each specific quote line detail.| |
| Billing & Pricing |**Journal line improvements** <br><br> This feature prevents creation of incorrect journal line entries by enforcing business rules. It introduces new validations and fills in dependent values automatically, based on the transaction class and transaction type. This feature aims to enhance the Quick Create form for journal lines by adding validations and defaulting logic for fields, as well as improving the display of fields.| |
| Time Entry |**Copilot in time entry (Generally Available)** <br><br> Copilot in time entry, which was originally released in USA only - will now be enabled by default in all regions, from this release onwards. Use Copilot to create time entries from assignments and generate external comments.| |
