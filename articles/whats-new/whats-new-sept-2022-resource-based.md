---
title: What's new September 2022 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the September 2022 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new September 2022 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.46.0.60
- Project management and accounting in a Dynamics 365 Finance environment version 10.0.29

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Opportunity Management | **Revision and Activation of Quotes**<br>Project Operations brings in the full support of the sales process. Project quotes can be activated to represent a state where the quote is read-only and is being reviewed. Activated quotes can be revised to create new quotes that have an incremented revision number. Activated project quotes or quote revisions can be closed as won or lost. | [Activate and revise a project quote](/dynamics365/project-operations/sales/activation-and-revision) |
| Billing and Pricing | **Time-zone agnostic price defaulting**<br>Project Operations has introduced the concept of a time-zone agnostic date on all project actuals. A new field, **Transaction date**, is now available on journal lines and actuals, and will be used to store the date when the transaction occurred, but without converting that date to Coordinated Universal Time. This date will be used for downstream processes such as price defaulting and invoice creation. | <p>[Determine cost rates for project-based estimates and actuals](/dynamics365/project-operations/pricing-costing/cost-price-resolution)</p><p>[Determine sales prices for project-based estimates and actuals](/dynamics365/project-operations/pricing-costing/sales-price-resolution)</p> |
| Billing and Pricing | **Date-effective price overrides in Project Operations**<br>Date-effective price overrides provide a way to override or change specific prices in the price list. | [Date-effective price overrides](/dynamics365/project-operations/pricing-costing/dateffective_price_overrides) |
| Subcontracting | **Subcontracting and vendor invoice reconciliation**<br>This feature enables customers to create subcontracts to purchase resource time, expense categories, and materials that are used for project work. It also enables customers to record, in finance and operations apps, vendor invoices that will be available to project managers in Dataverse for verification. | <p>[Subcontract management](/dynamics365/project-operations/pro/subcontracting/managing-subcontracts-overview)</p><p>[Create vendor invoices](/dynamics365/project-operations/procurement/vendor-invoicing-concept-and-creation)</p> |
| Time and Expense | **Global Approver**<br>This feature enables independent software vendor (ISV) and centralized approval, regardless of project or team member status in the project. | [Security and approvals](/dynamics365/project-operations/approvals/approvals-security) |
| Expense management | **Ability to post expense liability in vendor currency**<br>This feature enables expense reports to be posted in a vendor currency for the cash payment method. | [Ability to post expense liability in vendor currency](/dynamics365/project-operations/expense/posting-expense-reports#enable-the-ability-to-post-expense-liability-in-vendor-currency-for-cash-payment-method-feature) |
| Project Procurement | **Pay when paid vendor payments**<br>This feature enables the Pay when paid (PWP) feature to be used with Project Operations non-stock environments. It enables the vendor payments to be blocked/retained, based on retention terms, until the payment is received from the customer. | [Pay when paid vendor payments](/dynamics365/project-operations/procurement/pay-when-paid) |
| Project Procurement | **Project purchase requisitions**<br>This feature enables users to create project-related purchase orders in legal entities where Project Operations on Dynamics 365 Customer Engagement integration is enabled. Project purchase orders can be used to record non-stocked material procurement against the project by Procurement department persona. Project purchase orders won't be synced to Dataverse. However, you can use a virtual entity to surface Project purchase order lines in Dataverse for project manager information. Project-related vendor invoice cost is integrated with the Project Actuals entity in Dataverse. Project cost is recorded in the Project subledger by using the Project Operations Integration journal. | |
|Project Planning and Tracking|**Use Project schedule APIs to perform operations with Scheduling entities** </br> </br>The resource assignment contour editing API lets developers programmatically specify a task assignee's effort across any supported date range for more granular time phased effort planning.|[Use Project schedule APIs to perform operations with Scheduling entities](/dynamics365/project-operations/project-management/schedule-api-preview)|

## Project Operations dual-write maps updates

The following table shows the dual-write maps that have been modified or added in the September 2022 release of Project Operations.

| Entity map | Updated version | Comments |
| -------------- | ------------------- | ------------|
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.15 | This map supports the subcontract actuals processing with Project Operations for resource-based scenarios. |
| Project Operations integration project vendor invoice export entity (msdyn_projectvendorinvoices) | 1.0.0.2 | This map supports the subcontract actuals processing with Project Operations for resource-based scenarios. |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.5 | This map supports the subcontract actuals processing with Project Operations for resource-based scenarios. |

Always run the latest version of the map in your environment, and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you've customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Quality updates

### Project Operations on Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2754422 | Material and Expense estimates don't flow to Finance when projects are copied in Dataverse. |
| Time and Expense | 2787409 | A non-valid approver can approve a non-project time entry. |
| Opportunity Management | 2788907 | Updated error message on uniqueness validation for order lines that include flags. |
| Time and Expense | 2842253 | Null exception handling for time approval. |
| Billing and Pricing | 2844181 | Failure to get the correlation ID blocks invoice creation. |
| Billing and Pricing | 2876628 | QLD, CLD - Estimate price list resolution should use legacy date range fields of the price list. |
| Subcontracting | 2893222 | If no role is specified for a subcontract line, it should be possible to select that line on a team member for any role. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

## Features turned on by default in upcoming release

The following table lists the features that are turned on by default in version 10.0.30. Most features that have been automatically turned on can be turned off in [Feature management](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview). In the future, some features that have been automatically turned on might be removed from Feature management and become mandatory. This change ensures that customers are using current functionality, so that enhancements can build on the current functionality as they are added. Features will never be automatically enabled in less than one year, unless they are determined to be essential.

| Feature name | Enable date | Feature added | Feature state | Module |
| --- | --- | --- |--- |--- |
| Enable async operation when user needs to switch between sync and async operations | October 21, 2022 | April 9, 2021 | On by default | Expense management |
| Expense policy evaluation for receipts required | October 21, 2022 | December 20, 2021 | On by default | Expense management |
| List view of expense reports created by delegating workers | October 21, 2022 | February 19, 2020 | On by default | Expense management |
| Mileage totals calculation by fiscal year | October 21, 2022 | May 10, 2022 | On by default | Expense management |
