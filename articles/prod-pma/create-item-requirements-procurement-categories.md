---
title: Manage item requirements for procurement categories using purchase orders
description: Learn how to define project item requirements for procurement categories by using purchase orders, and how to generate project costs through product receipts for procurement categories.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: how-to
ms.custom: 
  - bap-template
ms.date: 04/15/2025
---

# Manage item requirements for procurement categories using purchase orders

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked based scenarios._

In Microsoft Dynamics 365 Finance, project item requirements are a crucial aspect of project management. They allow for planning and tracking of item consumption throughout the lifecycle of a project.

When a purchase order is created by using the **Item requirements** feature, Dynamics 365 Finance generates the project item requirements. Each purchase order line has a direct relationship with the project item requirement that is created for it.

This article explains how to use the **Item requirements** feature for purchase orders that are related to procurement categories. It lets customers issue project invoices for item requirements without having to wait for vendor invoices.

## Prerequisites

To use the feature for Dynamics 365 Project Operations for stocked based scenario, you must have the following versions:

- Finance version 10.0.44 or later

## Set up Project management and accounting parameters

To enable the **Item requirements** feature for project purchase order lines that are created for procurement categories, follow these steps:

1. Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **General** tab, set the **Create item requirement** option to **Yes**.
1. Set the **Create item requirement for procurement category** option to **Yes**.

    > [!NOTE]
    > The **Create Item requirement for procurement category** option becomes available only after you set the **Create item requirement** option to **Yes**. The system creates item requirement lines for project purchase order lines only if you set this option to **Yes**.

## Set up default sales categories for the procurement categories

To use the **Item requirements** feature for procurement categories, you must establish a relationship between the procurement categories and the sales categories, because item requirements support only sales categories.

To set up default sales categories for procurement categories, follow these steps:

1. Go to **Procurement and sourcing** \> **Procurement categories**.
1. On the Action Pane, select **Edit procurement hierarchy**.
1. On the **Assign procurement categories** tab, select the sales category that is related to the procurement category.

> [!NOTE]
> If you set the **Create item requirement for procurement category** option to **Yes** in the previous section, but the sales categories aren't linked to procurement categories, the system prevents the purchase order line from being saved and shows an error message.

After the setup is completed, the system creates item requirements that have a sales category for each purchase order line that is created for a procurement category. When the purchase order product receipt is posted, the system posts the item requirements packing slip for the quantity on the purchase packing slip. This process is similar to the process for service items or stocked items.

The system generates the project cost financials by using the purchase unit price and deducting any applicable purchase discounts. It also generates the project posted transactions.

In addition, if a sales price is available on the item requirements that are generated from the purchase order line, the system generates **WIP sales** and **accrue revenue** financial transactions.

Learn more about project purchase orders in [Purchase orders for a project](project-purchase-orders.md). Learn more about project purchase product receipts in [Project cost accrual on purchase receipts](/dynamics365/finance/accounts-payable/project-cost-accrual-purchase-receipts).
