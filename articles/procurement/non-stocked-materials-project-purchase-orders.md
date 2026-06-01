---
title: Order materials and services for a project using project purchase orders
description: Learn how you can use project purchase orders to order materials and services for a project.
author: sigitac
ms.author: mukumarm
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Order materials and services for a project by using project purchase orders

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations integrated deployments_

The procurement department in your organization might use [purchase orders](/dynamics365/supply-chain/procurement/purchase-order-overview) to track goods and services orders. You can attribute purchase orders for procurement categories or materials to a project. When invoicing these purchase orders, you record the cost against the project.

## Prerequisites

Complete the following steps to enable the project purchase orders functionality.

1. In Dynamics 365 Finance, go to the **Feature Management** workspace.
1. In the feature list, find and select the **Enable project purchase orders on Project Operations for resource based/non-stocked scenarios** feature. Select **Enable**.
1. In the feature list, find and select the **Enable stocked products usage for project operations integrated deployments** feature. This feature is required to use stocked products in integrated Project Operations deployments. Select **Enable**.
1. Configure non-stocked materials and pending vendor invoices as described in [Configure non-stocked materials and pending vendor invoices](configure-materials-nonstocked.md).
1. Configure procurement categories as described in [Use procurement categories with project purchase orders and pending vendor invoices](configure-procurement-categories.md).

## Create a project purchase order from the project purchase order list

1. In Finance, go to **Project management and accounting** > **Projects** > **All Projects** and select a project.
1. On the Action Pane, on the **Manage** tab, in the **New** group, select **Item task** > **Purchase order**.
1. On **Create purchase order**, select the vendor that you want to place the purchase order with, enter other information as appropriate, and then select **OK**.
1. On **Purchase order**, in the **Purchase order lines** grid, select **Add line**.
1. Enter an item number or procurement category, quantity, unit, unit price, and other information as appropriate.

    > [!NOTE]
    > Learn how to use stocked products in integrated deployments in [Managed stocked products for Project Operations integrated deployments](enable-stocked-products-integrated.md).

1. Continue to add items or procurement categories as required, and confirm the purchase order.

    You can record goods and services receipts by creating and posting a product receipt.

    > [!NOTE]
    > Product receipts aren't recorded to the project actuals in Microsoft Dataverse and don't impact the project subledger.

    After a vendor sends the invoice for items and services on the purchase order, the procurement department can generate an invoice for the purchase order by going to **Invoice** > **Generate** > **Invoice** on the Action Pane. For more information about pending vendor invoices, see [Purchase non-stocked materials using a pending vendor invoice](pending-vendor-invoices.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
