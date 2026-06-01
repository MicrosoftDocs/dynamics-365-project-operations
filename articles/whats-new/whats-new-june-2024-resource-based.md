---
title: What's new June 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the June 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - ms.custom:
  - evergreen
ms.date: 02/26/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new June 2024 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.105.0.13.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40.

## Project Operations Dual-write maps updates

The Dual-write maps associated with the 10.0.39 **Enable default financial dimensions for bookable** feature are included in this release.

- A change was made to add a new required key for references to Bookable Resource that is required for the maps listed below when updating map versions. From the **Dual-write** page, select **Integration key**. In the first column next to **Bookable Resource**, add the bookableresourceid [Bookable Resource] and select **Save**.
- The existing Project Operations integration actuals (msdyn_actuals) map has been updated to 1.0.0.18.
  - You may receive the error that "Project validation failed [DIPV1025] Missing destination field msdyn_bookableresource.bookableresourceid in the schema" upon activating the map version until you modify the key mapping describe earlier and then refresh tables.
- The existing Project Operations integration entity for hour estimates (msdyn_resourceassignments) map has been updated to 1.0.0.6.
  - You may receive an error until you modify the key mapping described earlier and then refresh tables.
- The Project worker resource import (bookable resources) is a new optional map specific to this feature. Note that it has a required dependency on the "Human Resources entity maps" Dual-write solution being installed.

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Financials | **(Preview) Enable flexibility in determining financial dimension defaulting** <br><br> This feature adds more flexibility in determining which financial dimensions should be posted using a new setup screen. This feature adds the ability to specify financial dimensions on the project contract for T&M contract lines.| [Financial dimension defaults](../project-accounting/financial-dimension-defaults.md)  |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Project Planning and Tracking|	3544700|	Project Save fails and you see the "The action on an assignment failed because it tried to update a nonexisting assignment." error when more than 5,000 assignments are updated or deleted.|
|Billing and Pricing|	3698404|	Price List Validations fail when creating Quote from opportunity.|
|Billing and Pricing|	3714531|	Actuals grid not calculating currency exchange rate properly.|
|Billing and Pricing|	3734257|	Use Transaction Date (Time zone independent) field instead of Document date during invoice creation. |
|Project Planning and Tracking|	3739067|	[PM defined project duration] Schedule API hardcodes 8 hours/day for duration field.|
|Sales|	3740721|	Estimated Cost Fields on the project can be updated manually via flow or API.|
|Project Planning and Tracking|	3795066|	Online: In GCC, users with a G3 or G5 license can't go to the Project App (they see a license error) and on the Project view, the left-hand nav is missing.|
|Approvals|	3807887|	Create new approval sets when reapproving entries with failed approval sets.|
|Time Management|	3843424|	Time entry of type Absence was created on the day before.|
|Billing and Pricing|	3877772|	Recalculate Totals silently fail when there are more than 50,000 records.|
|Project Planning and Tracking|	3880154|	Time out due to long running RefreshTeam request, while assigning a resource to multiple tasks.|
|Project Management|	3887432|	Online: PfW Risks form contains several duplicated fields (Project, Description, Mitigation Plan & Contingency Plan).|
|Sales|	3905161|	Error on project form if the new estimates tab was customized.|
|Resource Management|	3933397|	Task Wise score null for Availability Factor.|
|Billing and Pricing|	3944356|	Price records are being copied twice when closing a quote as won.|
|Approvals|	4097112|	Failed Approvals View shows processing approvals.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=936136&dbType=3&qc=4bfbc812bab8c497f0747156b4e6faa90d7d73b55226bc7406f2a9b71839162e).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
