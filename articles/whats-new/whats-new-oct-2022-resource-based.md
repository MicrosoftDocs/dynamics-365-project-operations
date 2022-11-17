---
title: What's new October 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the October 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.date: 11/17/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new October 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.57.0.176
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.30

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2316317|System allows to create invoice which has no chargeable transactions|
|Billing and Pricing|2737300|Validate for Customer field availability before accessing the form|
|Billing and Pricing|2744948|Add null check for Billing method|
|Billing and Pricing|2763515|Null reference error handle when sales contract of the invoice is missing|
|Billing and Pricing|2844301|Batch invoice creation fails due to an error|
|Billing and Pricing|2845869|Incorrect storage of Organization Service|
|Billing and Pricing|2853729|Role and Price details are updated when Billing type is modified|
|Billing and Pricing|2940350|We should default only active price lists when pricing Actuals|
|Deployment and Configuration|3001206|Entity - msdyn_replaylogheader is preventing upgrade of Customer Orgs|
|Opportunity Management|2755582|Null reference exceptions handle in Split Billing Rule Helper|
|Opportunity Management|2761477|When using split billing, deleting a milestone (header) leaves orphan milestones.|
|Opportunity Management|2767595|When a material usage record is opened in the main form, Bookable resource for the record is changed to the currently logged in user|
|Project Planning and Tracking|2790384|Pending OperationSet timeout is too short|
|Project Planning and Tracking|2957840|Unable to save tasks or add columns to the Tasks page in Integrated Project Operations|
|Resource Management|2751560|Inconsistent Preferred Organization Units in Resource Requirement |
|Subcontracting|2853245|Vendor Invoice Line actuals matching doesn't update the Verification Status if there is already a Contract Line linked to the VI Line|
|Subcontracting|2907231|Unable to advance process stage of vendor invoice.|
|Time and Expense|2867363|Records don't fall out of Absences/Vacations for Approval view when queued for approval|
|Time and Expense|2894405|TESA - Unused POC directory causing compliance issues|


### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.30. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they are added. Features will never be automatically enabled in less than one year, unless they are determined to be essential.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- |--- |--- |
| Enable async operation when user needs to switch between sync and async operations | October 21, 2022 | April 9, 2021 | On by default | Expense management |
