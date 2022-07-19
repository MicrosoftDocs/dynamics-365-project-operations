---
title: What's new July 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the July 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.date: 19/07/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new July 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.44.0.10
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.28

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Deployment and Configuration | 2761472 | PO Installation error handled. |
| Billing and Pricing |2746940 | Subcontract line name should have max length of 100 characters. |
| Billing and Pricing |2739162 | Customers must be able to see ribbon buttons on the actuals grid view. |
| Project Planning and Tracking | 2730318 |Updated validation for unsupported characters in Project Subject. |
| Billing and Pricing |2705361 | Milestone Billed Sales actuals must be included in Project Tracking Fields. |
| Billing and Pricing |2675880 | Prevent a project from being linked to a contract line that is not work based. |
| Billing and Pricing |2664396 | While saving a quote price list without quote, there must be an error stating that quote cannot be empty. |
| Billing and Pricing |2184019 | Task Based Billing tab should not show up for Projects with no backing Contract or Quote. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in 10.0.29. Most features that have been turned on atomically can be turned off in [Feature management](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been turned on automatically might be removed from Feature management and will become mandatory. This is to ensure that customers are using current functionality, so that as enhancements are added they can build on the current functionality. Features will never be automatically enabled in less than one year, unless they are determined to be essential.

| Feature name | Enable date | Feature added |Feature state| Module |
| --- | --- | --- |--- |--- |
|Enable adjustment of hour transaction </br>based on change in funding rule allocation | 09/16/2022 | 10/07/2020| On by default | Project management and accounting|
|Project purchase order prepayment </br>invoice reversal feature.|09/16/2022 |10/06/2021|On by default|Project management and accounting|
|Delete invoice proposal lines when </br>using Project Operations for </br>resource based/ non-stocked scenarios|09/16/2022|10/06/2021|On by default|Project management and accounting|
|Adjust accounting on a </br>posted project transaction|09/16/2022 |05/10/2020|On by default|Project management and accounting|
|Enable default accounting setup for project|09/16/2022|2/19/2020|On by default|Project management and accounting|
|Enable multiple contract lines for a project|09/16/2022|6/29/2020|On by default|Project management and accounting|
|Make Project Hour journals read-only </br>if current approval status doesn't allow editing.|09/16/2022 |10/06/2021|On by default|Project management and accounting|
|Enable sync sales lines from</br>purchase lines when purchase lines</br>are updated and purchase order</br>change management parameter is turned on|09/16/2022|10/07/2020|On by default|Project management and accounting|
|Enable Project Operations on</br> Dynamics 365 Customer Engagement|09/16/2022 |6/29/2020|On by default|Project management and accounting|
|Project transaction reversal correction feature|09/16/2022|7/13/2020|On by default|Project management and accounting|

## Features turned Mandatory in upcoming release

The following table lists the features that are mandatory from 10.0.29 onwards.
| Feature name | Enable date | Feature added |Feature state| Module |
| --- | --- | --- |--- |--- |
|Calculate the committed value on funding </br>source without rounding the exchange rate| 09/16/2022|6/14/2020|Mandatory|Project management and accounting|
|Enable project adjustment posting </br>with same ledger account as original transaction.|09/16/2022|6/14/2020|Mandatory|Project management and accounting|
|Project contract committed amount detail|09/16/2022|8/31/2019|Mandatory|Project management and accounting|
|Enable sorting by resource during </br>project invoice proposal creation|09/16/2022|8/31/2019 |Mandatory|Project management and accounting
