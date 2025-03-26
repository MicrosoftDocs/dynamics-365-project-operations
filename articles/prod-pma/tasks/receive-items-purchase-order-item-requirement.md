--- 
title: Use project item requirements with purchase orders
description: Learn how to manage and use project item requirements with purchase orders. 
author: mukumarm
ms.date: 03/25/2025
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: mukumarm
ms.search.validFrom: 2016-06-30 
ms.dyn365.ops.version: Version 7.0.0 
---

# Use project item requirements with purchase orders

[!INCLUDE[banner](../../includes/banner.md)]

This article provides guidance about how to use project item requirements with purchase orders.

In Microsoft Dynamics 365 Project management and accounting, *item requirements* refer to materials or products that are needed for a specific project. Those items can be procured, reserved, or issued from stock to fulfill project needs. By using an item requirement instead of an item transaction, you can plan for delivery just before the item is used, create a purchase order, include the item in the trade agreement framework, and include the item requirement in production planning.

## Understand how item requirements work in projects

- Item requirements are linked to a project and define the materials that are needed for project execution.
- Items can be fulfilled through inventory, purchase orders, or production orders.
- Transactions that are related to item requirements are tracked for project costing and revenue recognition.

## Link purchase orders to item requirements

Purchase orders can be linked to item requirements in two ways:

- First create an item requirement from the project. Then, if stock is unavailable, generate a purchase order from the item requirement to procure the needed materials.
- Create a purchase order directly. The item requirement is then automatically generated.

This process ensures that project costs are posted when materials are received. The system records the project cost by generating an item requirement packing slip upon receipt.

### Generate a purchase order from an item requirement

To generate a purchase order from an item requirement, follow these steps.

1. In Dynamics 365 Finance, go to **Project management and accounting** \> **Projects** \> **All projects**.
1. In the list, find the project, and select the link for it.
1. On the Action Pane, select **Plan**.
1. Select **Item requirements**.
1. Select **New**.
1. In the new row, in the **Item number** field, enter or select a value.
1. In the **Quantity** field, enter a number.
1. Select **Save**.
1. On the Action Pane, select **Manage**.
1. Select **Functions**.
1. Select **Create purchase order**.
1. Select the **Include all** checkbox.
1. In the **Vendor account** field, enter or select a value.
1. Select **OK**.

### Automatically generate item requirements from purchase order lines

To have item requirements automatically generated from purchase order lines, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **General** tab, set the **Create item requirements** and **Item consumption** options to **Yes**. When the **Item consumption** option is set to **Yes**, the item requirements packing slip is automatically generated after the corresponding purchase order packing slip is posted.

## Receive materials from purchase orders linked to item requirements

To receive materials from purchase orders that are linked to item requirements, follow these steps.

1. Go to **Accounts payable** \> **Purchase orders** \> **All purchase orders**.
1. In the list, find the purchase order, and select the link for it.
1. On the Action Pane, select **Purchase**.
1. Select **Confirm**.
1. On the Action Pane, select **Receive**.
1. Select **Product receipt**.
1. In the **Product receipt** field, enter a value.
1. Select **OK**.

The system automatically posts the item requirements packing slip and generates project transactions for cost and sales if item consumption is enabled in Project management and accounting parameters.

## Update project costs upon vendor posting

When item requirements are automatically posted during purchase order product receipt, the system considers the purchase price as the project cost. However, factors such as discounts, extra charges, or applied taxes sometimes cause the vendor invoice amount to differ from the purchase order price. In these cases, the project cost should be updated to reflect the changes.

### Update the project cost for stocked items

The project cost is updated through either the *inventory recalculation* process or the *inventory closing* process.

To update the project cost for stocked items or any item that is marked as stocked in the item model group, follow these steps.

1. Go to **Inventory management and accounting** \> **Periodic tasks** \> **Closing and adjustments**.
1. Select **Recalculation** to run the inventory recalculation process.
1. Select the date, and then select **OK** to run the process.

### Service items or procurement categories

No other setup or process is required to update the project cost for service items. The system automatically validates the project cost during purchase order receipt. If there is any deviation, the system updates the project cost accordingly.

In version **10.0.44**, a new feature was introduced: **Streamline project cost for service items and procurement categories with item requirements activated**. This feature automatically updates the project cost for service items to account for the impact of any discounts that are applied on the vendor invoice, any miscellaneous charges that are added to the invoice, or any price deviations. To help generate the project cost based on the vendor invoice, the feature considers the following factors:

- **Miscellaneous charges** – Miscellaneous charges can be added to vendor invoices to account for extra costs. They then affect the overall project cost. Any charge that is configured as a charge of the **Item** posting type updates the project cost during the vendor invoice posting process.
- **Discount amount or percentage** – Any new discount that is added on the vendor invoice updates the project cost during vendor invoice posting.
- **Price change** – Any price change on the vendor invoice updates the project cost during vendor invoice posting.
- **Tax amount** – The tax amount affects the project cost during vendor invoice posting, based on tax configuration settings such as nondeductible tax.

During the project invoicing process, this feature also ensures that only sales order lines are displayed from an invoicing perspective when purchase orders are generated from sales orders (excluding item requirements).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
