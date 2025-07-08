---
title: What's new September 2023 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the September 2023 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new September 2023 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.76.0.200
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.36

## Project Operations dual-write maps updates

There aren't any updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Proforma Invoicing| **Project invoicing usability and performance improvements**</br>This feature empowers project managers with the ability to swiftly revise invoices by selecting specific transactions for correction. This capability enhances the user experience, particularly in situations where only certain parts of the invoice require adjustment, sparing you the need to revise the entire amount.| [Project invoicing usability and performance improvements](/dynamics365/project-operations/proforma-invoicing/revise-project-invoices) |
|Opportunity Management| **Minimize the creation of roles and categories for performance**</br>This feature works to minimize this data creation to what’s included in the quote line details and ultimately what’s included in the associated project plan. In metadata updates, changes were made to quote and contract line forms to display both overrides and global tables. New and delete buttons were reinstated for override subgrids, and quote and contract line forms were added for all override types. The override main forms now include references to quote or contract lines. In UI, references for overrides are locked in noncreate forms, and unsupported billing type options like null, complimentary, and not available were removed.| |

## Features converted to parameters

The following table lists the features that are converted to parameter in version 10.0.36. These features can't be enabled from  [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) and are controlled by the parameters.

| Feature name | Module | More information|
| --- | --- | --- |
|Select project invoice proposal by funding source|Project management and accounting|This feature has been removed from feature management and moved to a parameter under the Contract tab of Project management and accounting parameters.|
|Enable the Invoice summary for Project invoice proposals and Project invoices.|Project management and accounting|This feature has been removed from feature management and moved to a parameter under the Invoice tab of Project management and accounting parameters. |

## Quality updates

### Project Operations on Dataverse

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

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=831854).
