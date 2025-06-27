---
title: What's new August 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the August 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new August 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.75.0.56
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.35

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Subcontracting|**Enhanced Vendor Invoice Verification** </br></br>This feature introduces new fields that let users view real-time 3-way match progress for a vendor invoice line and ensures more accurate verification of invoices. </br>To view these updates, enable the feature flag named **Enhanced Vendor Invoice Verification**. In subsequent releases, this feature introduces visualizations to track pending verification of invoice lines at the vendor invoice header level.| |

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3186838|Cost price list fails to default when the end date is outside the price list range.|
|Billing and Pricing|3233975|Imported estimate values don't match the estimates calculated on project.|
|Billing and Pricing|3370203|Validate ProjectParameterPriceList has a parameter reference.|
|Billing and Pricing|3419224|Material estimates should retain any price changes.|
|Opportunity Management|3107890|Transform the **Close as Lost** process for quotes into a long-running job and notify the user if the process is already in progress.|
|Project Management|2922153|When attempting to update the remaining effort for tasks, an error is thrown if the start date is later than the end date.|
|Project Management|3409749|Unable to modify the role of a team member created by a generic resource.|
|Project Management|3464455|Incorrect calculation of task start date due to Timezone difference in client and resource calendar.|
|Resource Management|3491774|Error received when using Specify Pattern on Team member grid.|
|Subcontracting|2920766|The Vendor field must be filled out when creating a subcontract, and it should throw an exception if left empty.|
|Subcontracting|3491867|Subcontract Line Resource creation leads to script error.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=817204&dbType=3&qc=d4c43f25691362609fd85d3d10e7a7123141638262fc87df2ac362ba5de8070b).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.36. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they're added. Features aren't automatically enabled in less than one year unless they're determined to be essential.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- |--- |--- |
|Enable to display the projects assigned to resources through the resource group in the mobile application.|September 15, 2023|May 22, 2023|On by default|Project management and accounting|
|Auto default **Intercompany project category** in expense mobile app.|September 15, 2023|April 20, 2022|On by default|Expense management|
|Use the new version of **Project forecast list** page.|September 15, 2023|May 22, 2023|On by default|Project management and accounting|
|Enable to make sure posted project transactions have the correct invoice status based on the contract billing rule setup.|September 15, 2023|October 3, 2021|On by default|Project management and accounting|
|Update labels for revenue recognition related forms and processes in Project Operations.|September 15, 2023|April 20, 2022|On by default|Project management and accounting|
|Keep project cost commitment for purchase requisition open until purchase order is confirmed.|September 15, 2023|April 29, 2021|On by default|Project management and accounting|
|Create project revenue recognition using multiple batch tasks.|September 15, 2023|January 9, 2021|On by default|Project management and accounting|
|Allow future transactions to be allocated to a budget in the current period.|September 15, 2023|January 9, 2021|On by default|Project management and accounting|
|Enable the project resource scheduling performance enhancement feature.|September 15, 2023|August 17, 2020|On by default|Project management and accounting|
|Project invoice proposal performance enhancement feature.|September 15, 2023|February 20, 2021|On by default|Project management and accounting|
|Enable to make sure the posted project transactions have the correct invoice status based on contract billing rule setup.|September 15, 2023|October 3, 2021|On by default|Project management and accounting|

## Features that become mandatory in the upcoming release

The following table lists the features that are mandatory from version 10.0.36 onward.

| Feature name | Feature added | Feature state | Module |
| --- | --- | --- | --- |
|Mileage totals calculation by fiscal year.|March 31, 2022|Mandatory|Expense management|
|Enable multiple contract lines for a project.|June 29, 2020|Mandatory|Project management and accounting|
|Enable Project Operations on Dynamics 365 Customer Engagement.|June 29, 2020|Mandatory|Project management and accounting|
