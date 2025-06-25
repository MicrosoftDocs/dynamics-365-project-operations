---
title: What's new 2024 wave 1 early access - Project Operations Integrated with ERP
description: This article provides information about the features available in the 2024 wave 1 early access release of Project Operations resource/non-stocked based scenarios deployment.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.author: tulsijhaveri
---

# What's new 2024 wave 1 early access - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.100.0.16
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Subcontracting | **Enhanced Vendor Invoicing Experience**<br><br>This feature introduces new fields that let users view real-time, three-way match progress for a vendor invoice line and ensures more accurate verification of invoices. This feature is now available as the default experience with Vendor Invoices. | &nbsp; |
| Subcontracting | **Enable subcontract actuals processing with Project Operations**<br><br>This feature allows the system to process subcontractor reported project actuals in the Project Operations integration journal. If the **Post product receipts to ledger in Account payable parameters** setting is enabled, system posts subcontract related actuals using the **Never ledger** principle. If the setting isn't selected, the system determines the posting method based on the Project cost and revenue profile setting for billable projects, or uses the Profit and loss posting method for internal projects. To use this feature, also enable the prerequisite **Transfer all lines with posting errors to a new Project Operations integration journal**. | [Create vendor invoices](../procurement/vendor-invoicing-concept-and-creation.md) |
| Project budget management | **Project budget management**<br><br>For resource/non-stocked deployment, you can create a budget in CE. To integrate the budget data with forecast data in Microsoft Dynamics 365 Finance, you need to enable the feature specifically in Dynamics 365 Finance, which is available in public preview.<br><br>As part of this early access release, the Project budget management feature is available by default. This means you can create, track, and revise both cost and sales budgets for your projects, and begin tracking actuals against these budgets. | [Project budget management overview](../pro/budget/projectbudgetmanagement.md) |
| Sales | **Sales - Modern quote**<br><br>The Modern Quote form is available by default. You won't need to enable the form via customization. | [New Quote form experience](../sales/quotes-new-form.md) |
| Procurement | **Use procurement categories in Project Operations**<br><br>This feature allows us to use procurement categories in project purchase orders and vendor invoices in legal entities with **Project Operations on Dynamics 365 Customer Engagement integration** enabled. The system determines transaction class to use for project actuals and project subledger based on the project category assigned to the procurement category record. | [Use procurement categories with project purchase orders and pending vendor invoices](../procurement/configure-procurement-categories.md) |
| Procurement | **Enable project purchase orders on Project Operations**<br><br>This feature allows users to create project related purchase orders in Legal entities with **Project Operations on Dynamics 365 Customer Engagement integration** enabled. Project purchase orders are used to record nonstocked materials procurement against the project by Procurement department persona. project purchase orders aren't synced to Dataverse, however you can use virtual entity to surface project purchase order lines in Dataverse for Project Manager information. Project related vendor invoice cost is integrated to the **Project Actuals** entity in Dataverse. Project cost is recorded in the project subledger using the Project Operations integration journal. | [Use project purchase orders in PO](../procurement/non-stocked-materials-project-purchase-orders.md)|

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Sales | **Modern Quote Nested Grid**<br><br>See quote lines and their quote line details all on the same grid, with the latter being in an expandable, nested grid. | [New Quote form experience](../sales/quotes-new-form.md) |
| Pricing | **Cost plus pricing**<br><br>Supported columns added to grid view in Price lists specifically for Role prices tab. | [Set up labor bill rates](../pro/pricing-costing/set-up-labor-bill-rate-sales.md) |
| Procurement | **Explore advanced subcontract capabilities**<br><br>Advanced subcontracting feature in Project Operations that seamlessly integrated with Dynamics 365 Finance. This feature lets users generate subcontracts, document timesheets, expenses, and other relevant information that subcontractors provide, in Dataverse. For every subcontract with Dataverse, the system automatically generates purchase orders in Dynamics 365 Finance. | [Subcontract purchase orders](../pro/subcontracting/subconpurchaseorders.md) |
