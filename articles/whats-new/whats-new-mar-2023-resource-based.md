---
title: What's new March 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the March 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new March 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.61.0.65
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.31

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Opportunity Management | **Support for all material pricing methods as supported by Microsoft Dynamics 365 Sales**<br>This feature helps customers of Dynamics 365 Project Operations set up sales prices for catalog products as a function of what it cost to procure the catalog product. Sales pricing methods supported for catalog products are at transaction cost, or a specified markup or markdown in addition to the transaction cost.| [Support for all material pricing methods as supported by Sales](/dynamics365/project-operations/pricing-costing/set-up-cost-sales-rates-materials). |


## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3071670|Estimates grid loads indefinitely.|
|Billing and Pricing|3125360|Errors occur when the length of the **msdyn ProductDisplayNamefield** is customized.|
|Billing and Pricing|3151655|The Refresh Invoice Line Transactions button does not bring up milestones that are ready to invoice.|
|Billing and Pricing|3169024|Customer and Org unit are not set correctly for business transactions without project.|
|Billing and Pricing|3169074|Across business transactions, the unit/unit group is not defaulted.|
|Billing and Pricing|3188076|When pressing enter or typing in search, the Time Unit in the Price List form generates an XML error.|
|Billing and Pricing|3207103|Exception handling while validating state.|
|Opportunity Management|2615847|An error occurs when updating the owner of a quote manually.|
|Project Planning and Tracking|3038418|Assigned contour effort display wrong value due to decimal inaccuracy.|
|Subcontracting|2990234|Auto confirmation of vendor invoice fails due to a OOB validation.|
|Subcontracting|3039300|Unable to get price defaulted based on Subcontract on a material usage log.|
|Subcontracting|3053577|Material Usage Log obtains prices from the Cost price list rather than the Purchase price list.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).
