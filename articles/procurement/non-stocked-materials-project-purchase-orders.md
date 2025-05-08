---
title: Order non-stocked materials for a project using project purchase orders
description: This article explains how you can order non-stocked materials for a project using project purchase orders.
author: sigitac
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Order procurement categories or non-stocked materials for a project using project purchase orders

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

The Procurement department in your organization might use [purchase orders](/dynamics365/supply-chain/procurement/purchase-order-overview) to track goods and services orders. Purchase orders for procurement categories or non-stock materials can be attributed to a project. Invoicing these purchase orders records the cost against the project.

## Prerequisites
Complete the following steps to enable the project purchase orders functionality.

1. In Dynamics 365 Finance, go to the **Feature Management** workspace.
2. In the feature list, find and select the feature, **Enable project purchase orders on Project Operations for resource based/non-stocked scenarios**.
3. Select **Enable**.
4. Configure non-stocked materials and pending vendor invoices as described in [Configure non-stocked materials and pending vendor invoices](configure-materials-nonstocked.md).
5. Configure procurement categories as described in [Use procurement categories with project purchase orders and pending vendor invoices](configure-procurement-categories.md).

## Create a project purchase order from the project purchase order list

1. In Finance, go to **Project management and accounting** > **Projects** > **All Projects** and select a project.
2. On the Action Pane, on the **Manage** tab, in the **New** group, select **Item task** > **Purchase order**.
3. On the **Create purchase order** page, select the vendor that you want to place the purchase order with, enter other information as appropriate, and then select **OK**.
4. On the **Purchase order** page, in the **Purchase order lines** grid, select **Add line**.
5. Enter an item number or procurement category, quantity, unit, unit price, and other information as appropriate.

    > [!NOTE]
    > Only procurement categories, non-stocked items, and services can be used with project purchase orders. Stocked items aren't supported.

6. Continue to add items or procurement categories as required, and confirm the purchase order.

    Goods and services receipts can be recorded by creating and posting a product receipt.

    > [!NOTE]
    > Product receipts aren't recorded to the project actuals in Microsoft Dataverse and don't impact the project subledger.

    After a vendor sends the invoice for items and services on the purchase order, the procurement department can generate an invoice for the purchase order by going to **Invoice** > **Generate** > **Invoice** on the Action Pane. For more information about pending vendor invoices, see [Purchase non-stocked materials using a pending vendor invoice](pending-vendor-invoices.md).
