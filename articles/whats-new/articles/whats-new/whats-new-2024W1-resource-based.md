---
title: What's new 2024 wave 1 early access - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the features available in the 2024 wave 1 early access release of Project Operations resource/non-stocked based scenarios deployment.
author: tulsijhaveri
ms.date: 02/22/2024
ms.topic: article
ms.prod:
ms.reviewer: 
ms.author: tulsijhaveri
---

# What's new 2024 wave 1 early access - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.100.0.16
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Subcontracting | **Enhanced Vendor Invoicing Experience**<br><br>This feature introduces new fields that let users view real-time 3-way match progress for a vendor invoice line and ensures more accurate verification of invoices. This will now be available as the default experience with Vendor Invoices. | &nbsp; |
| Subcontracting | **Enable subcontract actuals processing with Project Operations**<br><br>This feature will allow the system to process subcontractor reported project actuals in Project Operations integration journal. If Post product receipts to ledger in Account payable parameters setting is enabled, system will post subcontract related actuals using Never ledger principle. If the setting is not selected, the system will determine posting method based on the Project cost and revenue profile setting for billable projects or use Profit and loss posting method for internal projects. To use this feature please also enable the prerequisite Transfer all lines with posting errors to a new Project Operations integration journal. | [Create vendor invoices](https://learn.microsoft.com/en-us/dynamics365/project-operations/procurement/vendor-invoicing-concept-and-creation) |
| Project budget management | **Project budget management**<br><br>For resource/non-stocked deployment, you can create a budget in CE. To integrate the budget data with forecast data in F&O, you will need to enable the feature specifically in F&O, which will be available in public preview.<br><br>As part of this early access release, the project budget management feature will be available by default. This means you can create, track, and revise both cost and sales budgets for your projects, and begin tracking actuals against these budgets. | [Project budget management overview](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/budget/projectbudgetmanagement) |
| Sales | **Sales - Modern quote**<br><br>The Modern Quote form will be available by default. You will not need to enable the form via customization. | [New Quote form experience](https://learn.microsoft.com/en-us/dynamics365/project-operations/sales/quotes-new-form) |
| Procurement | **Use procurement categories in Project Operations**<br><br>This feature will allow us to use procurement categories in project purchase orders and vendor invoices in legal entities with Project Operations on Dynamics 365 Customer Engagement integration enabled. The system will determine transaction class to be used for project actuals and project subledger based on the project category assigned to the procurement category record. | [Use procurement categories with project purchase orders and pending vendor invoices](https://learn.microsoft.com/en-us/dynamics365/project-operations/procurement/configure-procurement-categories) |
| Procurement | **Enable project purchase orders on Project Operations**<br><br>This feature will allow user to create project related purchase orders in Legal entities with Project Operations on Dynamics 365 Customer Engagement integration enabled. Project purchase orders can be used to record non-stocked materials procurement against the project by Procurement department persona. Project Purchase Order will not sync to Dataverse, however you can use virtual entity to surface Project purchase order lines in Dataverse for Project Manager information. Project related vendor invoice cost is integrated to Project Actuals entity in Dataverse. Project cost is recorded in Project subledger using Project Operations Integration journal. | [Use project purchase orders in PO](https://learn.microsoft.com/en-us/dynamics365/project-operations/procurement/non-stocked-materials-project-purchase-orders)|

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Sales | **Modern Quote Nested Grid**<br><br>See quote lines and their quote line details all on the same grid, with the latter being in an expandable, nested grid. | [New Quote form experience](https://learn.microsoft.com/en-us/dynamics365/project-operations/sales/quotes-new-form) |
| Pricing | **Cost plus pricing**<br><br>Supported columns added to grid view in Price lists specifically for Role prices tab. | [Set up labor bill rates](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/pricing-costing/set-up-labor-bill-rate-sales) |
| Procurement | **Explore advanced subcontract capabilities**<br><br>Advanced subcontracting feature in Microsoft Dynamics 365 Project Operations that's seamlessly integrated with Dynamics 365 Finance. This feature lets users generate subcontracts, document timesheets, expenses, and other relevant information that subcontractors provide, in Dataverse. For every subcontract with Dataverse, the system automatically generates purchase orders in Finance. | [Subcontract purchase orders](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/subcontracting/subconpurchaseorders) |
