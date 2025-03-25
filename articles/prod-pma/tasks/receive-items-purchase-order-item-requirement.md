--- 
title: Use project item requirements with purchase orders
description: This article explains how to manage and use project item requirements with purchase order. 
author: mukumarm
ms.date: 03/21/2025
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines   
audience: Application User 
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: mukumarm
ms.search.validFrom: 2016-06-30 
ms.dyn365.ops.version: Version 7.0.0 
---

This article provides guidance on using project item requirements in conjunction with purchase orders.

In Microsoft **Dynamics 365 Project Management and Accounting**, **item requirements** refer to materials or products needed for a specific project. These items can be procured, reserved, or issued from stock to fulfill project needs. By using an item requirement instead of an item transaction, you can plan for delivery just before the item is used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning. 

# How Item Requirements Work in Projects
1. Item requirements are linked to a project and define the materials needed for execution.
2. Items can be fulfilled through inventory, purchase orders, or production orders.
3. Transactions related to item requirements are tracked for project costing and revenue recognition.

# Utilize item requirements alongside purchase orders. 

Purchase orders can be linked to item requirements in two ways:  

1. Create the item requirement from the project first, and if stock is unavailable, generate a purchase order to procure the needed materials.  
2. Create a purchase order directly, which automatically generates the item requirement.  

This process ensures that project costs are posted when materials are received. The system records the project cost by generating an item requirement packing slip upon receipt.

## Automatically generate item requirements from purchase order lines

To generate the item requirements automatically from a purchase order lines, below is the setup:

1. In **Dynamics 365 Finance**, Go to the **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
2. In the **General** tab, Mark **Create item requirements** and **Item consumption** to **Yes**. **In Dynamics 365**, the item requirements packing slip is automatically generated once the corresponding purchase order packing slip is posted if item consumption is marked to yes. 

## Generate purchase order from item requirement

1. In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.
2. In the list, select the link in the desired row.
3. On the Action Pane, select **Plan**.
4. Select **Item requirements**.
5. Select **New**.
6. In the new row, enter or select a value in the **Item number** field.
7. In the **Quantity** field, enter a number.
8. Select **Save**.
9. On the Action Pane, select **Manage**.
10. Select **Functions**.
11. Select **Create purchase order**.
12. Select the **Include all** check box.
13. In the **Vendor account** field, enter or select a value.
14. Select **OK**.

## Receive material from purchase orders linked with item requirements

1. In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.
2. In the list, select the link in the desired row.
3. On the Action Pane, select **Purchase**.
4. Select **Confirm**.
5. On the Action Pane, select **Receive**.
6. Select **Product receipt**.
7. In the **Product receipt** field, type a value.
8. Select **OK**.

The system automatically posts the item requirements packing slip and generates project transactions for cost and sales if item consumption is enabled in the Project Management and Accounting parameters.

## Update project costs upon vendor posting
When item requirements are posted automatically during the purchase order product receipt, the system considers the purchase price as the project cost. However, there are instances where the vendor invoice amount differs from the purchase order price due to factors such as discounts, additional charges, or applied taxes. In such cases, the project cost should be updated to reflect these changes.

### Stocked items
To update the project cost for stocked items or any item marked as stocked in the item model group, the project cost is updated through the **inventory recalculation** or **inventory closing process**.

1. In the navigation pane, go to **Modules > Inventory management and accounting > Periodic tasks > Closing and adjustments**.
2. Click **Recalculation** to run the inventory recalculation process.
3. Select the date and click OK to run the process. 

### Service items or procurement categories
No additional setup or process is needed to update the project cost for service items. The system automatically validates the project cost during the purchase order receipt, and if there is any deviation, it updates the project cost accordingly.

In version **10.0.44**, a new feature called **Streamline project cost for service items and procurement categories with item requirements activated** has been introduced. This feature accounts for the impact of discounts applied on the vendor invoice, any miscellaneous charges added to the invoice, or any price deviations, and automatically updates the project cost for service items. This feature helps to generate the project cost based upon vendor invoice considering below points:
1. **Miscellaneous charges** could be added to vendor invoices to account for these additional costs, which then impact the overall project cost. Any charge which is configured as posting type as item, updates the project cost during the vendor invoice posting process. 
2. **Discount amount, Discount percentage** any new discount added on the vendor invoice updates the project cost during the vendor invoice posting process.
3. **Price change** on the vendor invoice updates the project cost during the vendor invoice posting process.
4. **Tax amount** impacts the project cost based upon tax configuration settings like non-deductible tax during the vendor invoice posting process, 

This feature also ensures that during the project invoicing process, only sales order lines are displayed from an invoicing perspective when purchase orders are generated from sales orders (excluding item requirements).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
