---
title: What's new October 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the Oct 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.topic: conceptual
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 10/30/2024
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new October 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.121.0.50.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.41.

## Project Operations dual-write maps updates

There are no modifications to Dual-write maps in the Project Operations October 2024 release.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.


## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Financials |**Enable the use of Project fixed exchange rate agreements for resource/non-stocked deployments** <br><br> This feature provides the ability to optionally enter a fixed exchange rate on the project contract in Finance. This exchange rate will be used for converting the sales currency amounts into the legal entity's accounting currency.|[Use of fixed exchange rates](../invoicing/format-update-project-invoice-proposals.md) |
| Financials |**Enable project categories for on-account transactions** <br><br> This feature adds the ability to specify a project category for on-account transactions for resource/non-stocked deployment type. The use of project category allows for additional flexibility in recording revenue for different activities all recorded as milestones or other on-account transactions.|[Configure Project Categories](../project-accounting/configure-project-categories.md) |
| Project Budgeting |**Project budget time-phasing by Month, Quarter & Year** <br><br> This feature enhances project budget time-phasing capabilities. Previously, budget lines could only be time-phased in a weekly manner. With this release, project budget lines can now be time-phased by month, quarter, or year. The time-phasing method can be changed at the project level from weekly to monthly, quarterly, or yearly, but only when the budget version is in a draft or editable state to ensure data consistency.|[Set up budget period](../pro/budget/budget-period-setup.md) |
