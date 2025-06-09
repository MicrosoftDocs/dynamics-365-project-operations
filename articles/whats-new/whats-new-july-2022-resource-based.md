---
title: What's new July 2022 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the July 2022 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new July 2022 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.44.0.22
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.28

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Deployment and Configuration | 2761472 | A Project Operations installation error is handled. |
| Billing and Pricing | 2746940 | The subcontract line name should have a maximum length of 100 characters. |
| Billing and Pricing | 2739162 | Customers must be able to see ribbon buttons in the actuals grid view. |
| Project Planning and Tracking | 2730318 | Updated validation for unsupported characters in the project subject. |
| Billing and Pricing | 2705361 | Milestone billed sales actuals must be included in project tracking fields. |
| Billing and Pricing | 2675880 | Prevent a project from being linked to a contract line that isn't work-based. |
| Billing and Pricing | 2664396 | If a quote price list is saved without a quote, there must be an error that states that the quote can't be empty. |
| Billing and Pricing | 2184019 | The **Task Based Billing** tab should not be shown for projects that have no backing contract or quote. |
| Time and Expense | 2754459 | When recurrent scheduling cloud flow is inactive, show banner and bypass async processing. |
| Billing and Pricing | 2724391 | Wrong exception is thrown when project contract split billing rule is missing a customer value. |
| Billing and Pricing | 2708638 | Record was not found while searching using grid search in Material Usages and Approvals for Material Usages.|
| Billing and Pricing | 2686977 | Prevent validation for invoice line during invoice creation. |
| Billing and Pricing | 2683032 | Copying of chargeable roles and categories does not scale beyond 5000 records.|
| Billing and Pricing | 2673363 | Cost Consumption % on Project is corrupted when both Effort and Expense estimates and actuals exists for a project. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services (LCS), and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.29. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they are added. Features will never be automatically enabled in less than one year, unless they are determined to be essential.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- |--- |--- |
| Enable adjustment of hour transaction based on change in funding rule allocation | September 16, 2022 | October 7, 2020 | On by default | Project management and accounting |
| Project purchase order prepayment invoice reversal feature | September 16, 2022 | October 6, 2021 | On by default | Project management and accounting |
| Delete invoice proposal lines when using Project Operations for resource based/ non-stocked scenarios | September 16, 2022 | October 6, 2021 | On by default | Project management and accounting |
| Adjust accounting on a posted project transaction | September 16, 2022 | May 10, 2020 | On by default | Project management and accounting |
| Enable default accounting setup for project | September 16, 2022 | February 19, 2020 | On by default | Project management and accounting |
| Enable multiple contract lines for a project | September 16, 2022 | June 29, 2020 | On by default | Project management and accounting |
| Make Project Hour journals read-only if current approval status doesn't allow editing | September 16, 2022 | October 6, 2021 | On by default | Project management and accounting |
| Enable sync sales lines from purchase lines when purchase lines are updated and purchase order change management parameter is turned on | September 16, 2022 | October 7, 2020 | On by default | Project management and accounting |
| Enable Project Operations on Dynamics 365 Customer Engagement | September 16, 2022 | June 29, 2020 | On by default | Project management and accounting |
| Project transaction reversal correction feature | September 16, 2022 | July 13, 2020 | On by default | Project management and accounting |

## Features that become mandatory in the upcoming release

The following table lists the features that are mandatory from version 10.0.29 onward.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- | --- | --- |
| Calculate the committed value on funding source without rounding the exchange rate | September 16, 2022 | June 14, 2020 | Mandatory | Project management and accounting |
| Enable project adjustment posting with same ledger account as original transaction | September 16, 2022 | June 14, 2020 | Mandatory | Project management and accounting |
| Project contract committed amount detail | September 16, 2022 | August 31, 2019 | Mandatory | Project management and accounting |
| Enable sorting by resource during project invoice proposal creation | September 16, 2022 | August 31, 2019 | Mandatory | Project management and accounting |
