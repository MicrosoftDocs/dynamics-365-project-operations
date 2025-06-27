---
title: What's new September 2023 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the September 2023 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new September 2023 - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.76.0.200

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Proforma Invoicing| **Project invoicing usability and performance improvements**</br>This feature empowers Project Managers with the ability to swiftly revise invoices by selecting specific transactions for correction. This capability enhances the user experience, particularly in situations where only certain parts of the invoice require adjustment, sparing you the need to revise the entire amount.| [Project invoicing usability and performance improvements](/dynamics365/project-operations/proforma-invoicing/revise-project-invoices) |
|Opportunity Management| **Minimize the creation of roles and categories for performance**</br>This feature works to minimize this data creation to what’s included in the quote line details and ultimately what’s included in the associated project plan. In metadata updates, changes were made to quote and contract line forms to display both overrides and global tables. New and Delete buttons were reinstated for override subgrids, and quote and contract line forms were added for all override types. The override main forms now include references to quote or contract lines. In UI, references for overrides are locked in noncreate forms, and unsupported billing type options like null, complimentary, and not available were removed.| |

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3235616|Update ImportConfig.xml file with solution hints.|
|Billing and Pricing|3508349|Journal Line with no Sales Contract causes unhelpful **Key Not Found** error during pricing.|
|Billing and Pricing|3529600|Remove delete of quote line details from pre validate quote delete plugin.|
|Billing and Pricing|3530621|Not to exceed incorrectly reevaluated to Failed.|
|Deployment and Configuration|3526949|Fix Upgrade Readiness issue with Duplicate CustomAction ID in RibbonDiff.|
|Deployment and Configuration|3540616|Localized string is too long for import in German language pack.|
|Horizontals|3442847|Risk Register Grid doesn't refresh with risks when risks are created from Copilot.|
|Opportunity Management|3566033|Winning a quote fails with Null Reference Exception.|
|Project Management|3467461|Deep links to Tasks don't work when the Accelerator is installed.|
|Project Management|3511697|Disable ATM plugins registered on Associate & Disassociate (of all entities) to prevent large async backlog.|
|Project Planning and Tracking|3492526|Copilot tab showing up in project import window.|
|Project Planning and Tracking|3520700|msdyn_autoscheduling field in deprecated component solution shouldn't be Required.|
|Project Service|3543997|Project history ownership should always update when project ownership changes.|
|Resource Management|3491772|Error received when using Specify Pattern on Team member grid.|
|Time and Expense|3251783|Message incorrectly displayed: "There are no appointments found between the selected dates" when trying to import time entries.|
