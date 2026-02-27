---
title: What's new July 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the July 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 02/26/2026
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new July 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.74.0.59
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.35

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the Project Operations July 2023 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.16 | This change ensures the transaction date doesn't shift in the situations when a user entering a transaction resides in the timezone different from UTC. The change only effects approved actuals following the activation of the new dual write map. Transactions that were created or processed prior to this update remains unaffected, and there won't be an impact or changes applied to them. |

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3252938|Check for presence of tabs before setting visibility.|
|Billing and Pricing|3340535|Transaction Category not being maintained in actuals created from approved Material usage logs or Time Entries.|
|Billing and Pricing|3349398|Null reference exception when updating/deleting custom-created estimate lines.|
|Billing and Pricing|3377810|Material transaction could get priced from category price.|
|Billing and Pricing|3432590|Update Error Message for Quote and Contract Price List Validation.|
|Billing and Pricing|3445803|Update Dual write actuals map to sync Dataverse msdyn_transactiondate field to Dynamics 365 Finance DOCUMENTDATE field.|
|Billing and Pricing|3459402|Expose Journal Preview API to be invoked from customization.|
|Billing and Pricing|3459403|Expose Journal Confirm API to be invoked from customization.|
|Opportunity Management|3423900|Price list overlaps not validated when quote/contract price list is updated.|
|Opportunity Management|3423917|Entity price lists aren't validated when entity is changed.|
|Project Planning and Tracking|3259681|Estimates not being copied when the project is copied.|
|Project Planning and Tracking|3367034|Change Project Label name using Project Schedule API via Power Automate.|
|Resource Management|3209488|Adding Named Team Members to a Project For Non-Stocked Scenarios is incorrectly defaulting the TM's owning company.|
|Resource Management|3477979|Project Operations Package Deployment failing in UR35 Integrated Org.|
|Subcontracting|3208659|The loss of Project Category information in Vendor Invoice when it flows into Dataverse results in accounting problems within the Project integration journal.|
|Subcontracting|3236886|Unbilled Sales created with price zero during Vendor Invoice Confirmation when currency of contract is different from VI's currency.|
|Subcontracting|3338245|Posting vendor invoice fails when lines include Procurement category with category type Item.|
|Subcontracting|3445436|When a Bookable Resource doesn't have a specified Worker Type, an incorrect WorkerType is displayed on the Team tab of Project.|
|Time and Expense|3284355|No receipt is available for a submitted expense.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=805875).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.36. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they're added. Features aren't automatically enabled in less than one year unless they're determined to be essential.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- |--- |--- |
|Enable to display projects assigned to resources through the resource group in the mobile application.|September 15, 2023|May 22, 2023|On by default|Project management and accounting|
|Auto default "Intercompany project category" in expense mobile app.|September 15, 2023|April 20, 2022|On by default|Expense management|
|Use new version of Project forecast list page.|September 15, 2023|May 22, 2023|On by default|Project management and accounting|
|Enable to make sure posted project transactions have correct invoice status based on contract billing rule setup.|September 15, 2023|October 3, 2021|On by default|Project management and accounting|
|Update labels for revenue recognition related forms and processes in Project Operations.|September 15, 2023|April 20, 2022|On by default|Project management and accounting|
|Keep project cost commitment for purchase requisition open until purchase order is confirmed.|September 15, 2023|April 29, 2021|On by default|Project management and accounting|
|Create project revenue recognition using multiple batch tasks.|September 15, 2023|January 9, 2021|On by default|Project management and accounting|
|Allows future transactions to be allocated to a budget in the current period.|September 15, 2023|January 9, 2021|On by default|Project management and accounting|
|Enable project resource scheduling performance enhancement feature.|September 15, 2023|August 17, 2020|On by default|Project management and accounting|
|Project invoice proposal performance enhancement feature.|September 15, 2023|February 20, 2021|On by default|Project management and accounting|
|Enable to make sure posted project transactions have correct invoice status based on contract billing rule setup.|September 15, 2023|October 3, 2021|On by default|Project management and accounting|

## Features that become mandatory in the upcoming release

The following table lists the features that are mandatory from version 10.0.36 onward.

| Feature name | Feature added | Feature state | Module |
| --- | --- | --- | --- |
|Mileage totals calculation by fiscal year.|March 31, 2022|Mandatory|Expense management|
|Enable multiple contract lines for a project.|June 29, 2020|Mandatory|Project management and accounting|
|Enable Project Operations on Dynamics 365 Customer Engagement.|June 29, 2020|Mandatory|Project management and accounting|
