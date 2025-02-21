---
title: What's new February 2025 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the February 2025 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 02/20/2025
ms.reviewer: johnmichalak

---

# What's new February 2025 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.124.0.1450.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.42.

## Project Operations dual-write maps updates

The following table shows the Dual-write maps that are modified or added in the Project Operations March 2024 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration contract line milestones (msdyn_contractlinescheduleofvalues) | 1.0.0.6 | Latest version updated |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Mobile App** <br><br> Project team members on Lite and resource/Non stocked-based deployments of Project Operations now have a new mobile application based on Microsoft Power Apps. The new mobile app helps them log time, keep track of submitted entries, and view work assigned to them. |[Time Entry Mobile App](../time/time-entry-mobile-app-overview.md) |
| Sales |**Time phasing of Sales Estimates** <br><br> The Time phasing of prices feature provides visibility into price fluctuations over time within project quote lines and project contract lines. Nested quote line details display price changes phased out on a weekly basis, allowing you to track adjustments due to price overrides or multiple price lists.| [Estimate a project quote line](../sales/create-estimate-quote-line.md) <br> [Estimate a project contract line](../sales/create-estimate-contract-line.md) |
| Invoicing |**Progress Billing in Billing hub** <br><br> | [Progress billing within Billing Hub](../proforma-invoicing/billing-hub.md) |
| Billing |**Progress billing in integrated deployments** <br><br> |[Create invoice schedules for a project-based contract line](../sales/invoice-schedules-contract-line.md) <br> [Project Contract Lines Overview](../sales/manage-contract-values-project-based-sales.md)|
| Invoicing |**Processing billed sales in integrated deployments** <br><br> |[Add new invoice line details](../proforma-invoicing/add-new-ild-to-invoice.md)  |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Billing and Pricing|	3272365|	Updated Time & Material Backlog Filters to only reflect actuals that can be invoiced|
|Project Planning|	3740986|	PEntityGuard blocks Project.AttributeMsdyn_MSProjectDocument at Create|
|Billing and Pricing|	4152179|	Estimates OneGrid quick create form throws exception if no default unit/unit group exists|
|Billing and Pricing|	4187521|	Invoice revision copies fields that cause privilege exception|
|Billing and Pricing|	4211979|	Invoice Line Detail correction field can be true even when original Invoice Line Detail is blank|
|Approvals|	4438571|	Project Approver role lacking sufficient privileges to view approvals|
|Subcontracting|	4480942| The Product in CE is mapped to wrong Company when data is synchronized with DualWrite|
|Subcontracting|	4481246|	Actual reevaluation: Vendor Invoice Cost Actuals Are Missing Fields|
|Subcontracting|	4481635|	Actual reevaluation: All Vendor Invoice Actuals Are Reversed When Task Deleted|
|Subcontracting|	4484351|	Can't correct actuals from canceled vendor invoice|
|Billing and Pricing|	4498838|	"Effective date" is impacted by local time zone, on the price override bulk create dialog|
|Sales|	4504727|	Deleting Revised Milestone Prevents Invoices From Importing To Finance & Operations|
|Billing and Pricing|	4508856|	Changing Project on Contract Line fails due to lack of permissions for msdyn_longrunningjobstatus|
|Billing and Pricing|	4511507|	Disallow changes to Project invoice status from confirmed (or paid) to "In review" or any out of the box status|
|Billing and Pricing|	4511677|	Handle error when transaction classification is missing on the Invoice Line Detail when confirming invoice|
|Time Entry|	4521147|	Modern Time Entry Grid text still shows up in English in non English base language environments|
|Billing and Pricing|	4524095|	Quantity is cleared on journal line main form open|
|Sales|	4529109|	Invoice schedule type isn't redefaulted when billing method is updated on quote line|
|Project Budgeting|	4546764|	Fix unit conversion on merging of budget lines during budget import & summarization|
|Project and Resource Management|	4594360|	When Allow percent complete is No, and when a task is marked as completed, schedule variance is not getting updated.|
|Billing and Pricing|	4606728|	Unable to view milestones backlog in Billing hub|
|Sales|	4625154|	Recalculate button not is working on Quotes and Contracts|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=971730&dbType=3&qc=10e8ad5ad029bad3a0c2faa0e2dfc5d699a64ad8bfd2d1af37a5a02bb5800efa).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
