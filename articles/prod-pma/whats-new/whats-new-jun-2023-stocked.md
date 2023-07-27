---
title: What's new or changed in Project Operations, June 2023 for stocked/production-based scenarios
description: This article provides information about the quality updates that are available in the June 2023 release of Microsoft Dynamics 365 Project Operations for stocked/production-based scenarios.
author: ramagadu
ms.date: 06/21/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# What's new or changed in Project Operations, June 2023 for stocked/production-based scenarios

_**Applies To:** Project Operations for stocked/production-based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.34

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Expense Management| **Expense Mobile - Intuitive Expense Entry (Public Preview)**</br>The Expense mobile app is a powerful solution that's designed to simplify and enhance the expense reimbursement process and increase user productivity. Thanks to its focus on being intuitive and easy to use, the Expense mobile app offers a range of features that make reporting expenses seamless and efficient.| [Expense Mobile - Intuitive Expense Entry](/dynamics365/project-operations/expense/new-expense-mobile-app-overview) |
|Project Invoicing| **Enable packing slip cancellation for item requirements (Public Preview)**</br>This feature changes how financial posting is done for stocked item requirements to closely resemble sales order postings. It also changes how inventory is posted for stocked items and changes the behavior to have the line status of posted item requirements as delivered instead of invoiced. All of these changes have been made in support of enabling users to cancel packing slips for an item requirement.| [Enable packing slip cancellation for item requirements](/dynamics365/project-operations/prod-pma/project-item-requirements) |

## Quality updates

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=805875).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.36. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they're added. Features aren't automatically enabled in less than one year, unless they're determined to be essential.

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

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- | --- | --- |
|Mileage totals calculation by fiscal year|September 15, 2023|May 10, 2022|Mandatory|Expense management|
