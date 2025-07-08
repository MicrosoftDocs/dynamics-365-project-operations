---
title: What's new February 2022 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the February 2022 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new February 2022 - Project Operations Integrated with ERP

*Applies To: Project Operations Integrated with ERP*

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.28.0.120
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.24

## Features included in this release

- As of this release, you can add up to 300 team members to a single project. Previously, the limit on the number of team members was 150. For more information, see [Project limits](../project-management/project-and-task-limitations.md).

## Project Operations dual-write map updates

The following list shows the dual-write maps that have been modified or added in the Project Operations February 2022 release.

| Entity map | Updated version | Comments |
| --- | --- | --- |
| Project Operations integration project expenses export entity (msdyn\_expenses) | 1.0.0.3 | Extended for project activity synchronization to Dataverse. |

For the current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual Write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and pricing | 2415109 | The default value in the **Operations payment terms** field must be the project contract customer record and the proforma invoice record. |
| Billing and pricing | 2497369 | Material correction must follow the date value in the **Correction** parameters. |
| Billing and pricing | 2498697 | Improved the security configuration for **Time entry recall**. |
| Billing and pricing | 2513824 | For resource-based scenarios, the transaction category ID must not exceed 28 characters in Project Operations. |
| Billing and pricing | 2517455 | The **Refresh invoice line transactions** action must not be allowed to be triggered multiple simultaneous times for the same invoice. |
| Billing and pricing | 2517465 | The **Deactivate invoice line details** action is blocked because it isn't supported. |
| Billing and pricing | 2556660 | Fixed the date effectivity check that is done on the price list that is attached to a project parameters record. |
| Opportunity management | 2369202 | Corrected the business logic that verifies that price lists that have overlapping effectivity dates can be attached to the same project contract. |
| Opportunity management | 2385965 | Corrected the behavior on the **Customers** tab of the **Project contract** page when you select **Save and close**. |
| Time and expense | 2538503 | A project task must be available in the **Project actuals** entity after an expense report is posted. |

### Project management and accounting on Dynamics 365 Finance

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Project management and accounting | [615496](https://fix.lcs.dynamics.com/Issue/Details/?bugId=615496) | During import of vendor credit notes, an error occurs. The error message states, "Retainage amount can't be more than remaining net amount." |
| Project management and accounting | [619391](https://fix.lcs.dynamics.com/Issue/Details/?bugId=619391) | If an invoice proposal includes any zero-amount fee transactions that are unbilled sales actuals, invoicing can't occur. |
| Project management and accounting | [624423](https://fix.lcs.dynamics.com/Issue/Details/?bugId=624423) | The posted cost isn't correct after the purchase price is updated and **Activate change management** is enabled.|
| Project management and accounting | [628386](https://fix.lcs.dynamics.com/Issue/Details/?bugId=628386) | The posting estimate for a fixed-price project uses the incorrect currency and amount in the estimate voucher, even when the **Enable project contract currency for estimate calculation** feature is enabled. |
| Project management and accounting | [629239](https://fix.lcs.dynamics.com/Issue/Details/?bugId=629239) | **ProjDMFDataPopulation\_Extension** shouldn't make a call to enable change tracking without catching exceptions for entities that have configuration keys that aren't enabled. |
| Project management and accounting | [623818](https://fix.lcs.dynamics.com/Issue/Details/?bugId=623818) | The batch job is fixed when multiple advanced journals are posted and an error occurs. |
| Travel and Expense | [616805](https://fix.lcs.dynamics.com/Issue/Details/?bugId=616805) | Because of a settlement issue that is related to cash advances on expense reports, the tax amount isn't covered as part of the cash advance. |
| Travel and Expense | [616959](https://fix.lcs.dynamics.com/Issue/Details/?bugId=616959) | Sales tax information isn't included on the **Expense - Posted transactions** report. |
| Travel and Expense | [618943](https://fix.lcs.dynamics.com/Issue/Details/?bugId=618943) | The **Receipts Required** expense policy violation incorrectly shows a warning on expense reports. |
| Travel and Expense | [633470](https://fix.lcs.dynamics.com/Issue/Details/?bugId=633470) | A project transaction doesn't include nonrecoverable sales tax in the total sales amount when the transaction is a result of a mileage expense. |
| Travel and Expense | [642979](https://fix.lcs.dynamics.com/Issue/Details/?bugId=642979) | When an itemized line has tax, you can't change the itemization line date, and a source document state error occurs. |

## Removed and deprecated features

The [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) article describes features that have been removed or deprecated for Dynamics 365 Project Operations.

- A removed feature is no longer available in the product.
- A deprecated feature isn't in active development and might be removed in a future update.

A deprecation announcement appear in the [Removed or deprecated features in Project Operations](removed-depreciated-features-project.md) article 12 months before any feature is removed from the product.

For breaking changes that only affect compilation time, but are binary compatible with sandbox and production environments, the deprecation time will be less than 12 months. Typically, these changes are functional updates that must be made to the compiler.
