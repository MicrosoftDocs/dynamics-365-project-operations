---
title: What's new June 2024 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the June 2024 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.topic: conceptual
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 06/13/2024
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new June 2024 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.105.0.5.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40.

## Project Operations dual-write maps updates

_There are no Dual-write maps that are modified or added in the Project Operations June 2024 release._

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](https://github.com/MicrosoftDocs/dynamics-365-project-operations-pr/blob/PO_RN_UR39_Nov23/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](https://github.com/MicrosoftDocs/dynamics-365-project-operations-pr/blob/PO_RN_UR39_Nov23/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Financials | **(Preview) Enable flexibility in determining financial dimension defaulting** <br><br> This feature adds additional flexibility in determining which financial dimensions should be posted using a new setup screen. Additionally, this feature adds the ability to specify financial dimensions on the project contract for T&M contract lines.| [Financial dimension defaults](../project-accounting/financial-dimension-defaults.md)  |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3586943|	Estimate grid to show update to prices and Billing type (chargeability) when "Update prices" is selected.|
|Billing and Pricing|	3734257|	Use Transaction Date (Time zone independent) field instead of Document date during invoice creation. |
|Sales|	3749382|	Close As Won fails if QuoteLineResourceCategory is pointing to Inactive ResourceCategory record.|
|Billing and Pricing|	3761980|	Recalculate API on invoice doesn't recalculate the Chargeable amount, Nonchargeable amount, etc.|
|Project Planning and Tracking|	3764826|	Copy Project has team members copied to the root business unit.|
|Approvals|	3801469|	Project approval billing type is only set with linked contract line.|
|Sales|	3815475|	Able to create and update estimate lines with invalid subcontract lines.|
|Billing and Pricing|	3817244|	Invoice with missing invoice lines is created when Project Contract has more than 5,000 contract lines (Project based lines + Product based lines).|
|Project Management|	3838992|	 Status reports displayed on the screen and as part of printed content are fully accessible.|
|Billing and Pricing|	3852034|	Billing hub doesn't reflect correct amount for the **Fee** field, nor does it show the unbilled sales transactions of type **Fee** when selected. |
|Project Contracts|	3859490|	Error with contract performance tab when contract is created without project.|
|Billing and Pricing|	3876272|	Invoice confirmation fails with error **An item with the same key is already added**.|
|Project Budgeting|	3884108|	During Revision Recreate Details for Expanded Budget Lines.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=886261).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
