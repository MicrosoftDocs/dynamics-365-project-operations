---
title: What's new February 2023 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the February 2023 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new February 2023 - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.60.0.112
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.31

## Project Operations dual-write maps updates

There are no updates for Project Operations dual-write maps in this release. For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Opportunity Management | **Allow the modification of Billing Method on Quote**<br>This feature changes the default behavior of the Quote to allow the user to update the Quote Line Billing Method, as long as there aren't any pending transactions.| [Allow the modification of Billing Method on Quote](/dynamics365/project-operations/pro/sales/quotes-key-concepts-sales#billing-method) |
| Project Planning and Tracking | **Resource Assignment Contour Editing Enhancements**<br>The contour editing grid has been enhanced to include the ability to group contours by week. We have also added previous and next controls to support quickly changing periods in the current view. Lastly, we also added a grand total row.| [Create resource assignments](/dynamics365/project-operations/project-management/create-assignments) |
| Project Planning and Tracking | **Schedule API Operation Set Details Limit Increase**<br>The Operation set detail limit has been increased from 100 to 200. | [Use Project schedule APIs to perform operations with Scheduling entities](/dynamics365/project-operations/project-management/schedule-api-preview) |
| Project Planning and Tracking | **Work Breakdown Structure Save Performance Improvements**<br> For larger or more complex work breakdown structures, we have provided significant performance gains in save execution to Dataverse.||
| Billing and Pricing | **Bulk confirm of Invoices**<br> This feature provides customers the ability to bulk-confirm project invoices.|[Bulk-confirm proforma project-based invoices](/dynamics365/project-operations/proforma-invoicing/bulk-confirm-project-invoices) |
| Billing and Pricing | **Performance improvements in Estimates pricing**<br> This feature helps customers see improved performance during pricing of resource time estimates using a newly introduced parameter to price estimates on-demand. |[Performance improvements in Estimates pricing](/dynamics365/project-operations/project-management/resource-estimates#performance-improvements-in-estimates-pricing) |


## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2751655|Unable to correct Project task in expense entry using journal.|
|Billing and Pricing|2844301|Batch invoice creation fails due to an error.|
|Billing and Pricing|2916713|Following the revaluation of the actuals, the validation logic for checking project and contract contracting units is executed.|
|Billing and Pricing|2952110|Deleting Materials entry leaves orphan journal line records.|
|Billing and Pricing|3024964|It should not be possible to attach a project price list in a different currency to a quote or contract.|
|Billing and Pricing|3137848|Confirming a journal line for Retainer or Milestone sets Project contract and contract line to null.|
|Billing and Pricing|3142664|Use shared variable to allowlist Invoice Correction plugin from going through validations.|
|Opportunity Management|2991480|Change the "RequestedDeliveryDateNotSpecified" error message to point to the "Requested delivery date" as a field on the contract form.|
|Opportunity Management|3079232|Quote copy corrupts the data - creates project line related data for product lines.|
|Opportunity Management|3194627|Unable to list Categories of Expense Estimates.|
|Project Budgeting And Forecasting|3161616|An insufficient privileges error dialog was displayed when loading Project entity record.|
|Project Operations Upgrade|3135362|PSA to PO Upgrade\Data Validation: Increase the limit on resources per project from 150 to 300.|
|Project Operations Upgrade|3145341|Upgrade from PSA to latest PO v4 fails randomly.|
|Project Planning and Tracking|2423016|When the work hour template does not have a calendar assigned, a meaningful error is displayed.|
|Project Planning and Tracking|3044268|Resource's Parents and Resource's Children are missing from Pool/Crew Bookable Resource in 4.x.|
|Project Planning and Tracking|3055317|Project scheduler update validator does not work expectedly.|
|Project Planning and Tracking|3138011|Editing Effort Remaining in the Tracking Grid is no longer possible.|
|Project Planning and Tracking|3144016|Resource Reconciliation Grid Shows ISV Error when trying to Extend Bookings of too small a size.|
|Project Planning and Tracking|3183764|The Estimates/Resource Assignments tab does not appear in the integrated environment.|
|Resource Management|2520133|Handle a null-ref exception when attempting to create a Bookable Resource of type **Pool**.|
|Subcontracting|2928579|Unbilled sales actuals are 0 for an expense when the sales price is set at cost or as a markup over cost.|
|Time and Expense|3034892|When you reselect **Overtime** or **Work**, the project field does not repopulate.|

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).
