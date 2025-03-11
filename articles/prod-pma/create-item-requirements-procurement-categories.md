---
title: Manage item requirements for procurement categories using purchase orders
description: Discover how to define project item requirements for procurement categories using purchase orders and generate project costs through product receipts for procurement categories.
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

In **Dynamics 365 Finance**, project **item requirements** are a crucial aspect of **project management**, allowing for the planning and tracking of **item consumption** throughout the lifecycle of a project. 
When a **purchase order** is created using the **item requirements** feature, **Dynamics 365 Finance** generates the project item requirements. Each **purchase order** line has a direct relationship with the project **item requirement** created for that line. 

This article outlines how to use the item requirements feature for purchase orders related to procurement categories. It enables customers to issue **project invoices** for **item requirements** without waiting for vendor invoices.

## Prerequisites

To use the feature for Dynamics 365 Project Operations for stocked based scenario, you must have the following versions:

- Finance version 10.0.44 or later

## Set up project management and accounting parameters

To enable the item requirements feature for project purchase order lines created for procurement categories, follow these steps.

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1. Select the **General** tab.
1. Mark **Create item requirement** to **Yes**.
1. Mark **Create item requirement for procurement category** to **Yes**.

> [!NOTE] 
> **Create Item requirement for procurement category** is enabled for selection only after selecting the **Create Item Requirements** option. If this option isn't selected, the system doesn't create the **item requirement** lines for the **project purchase order** lines.

## Set up default sales categories for the procurement categories

To use the **item requirements** feature for **procurement categories**, you need to establish a relationship between the **procurement category** and the **sales category**, as item requirements only support sales categories.

To set up default sales categories for the procurement categories, follow these steps.

1. Go to **Procurement and sourcing** > **Procurement categories**.
1. On the action pane, select **Edit procurement hierarchy**.
1. On the **Assign procurement categories** tab, select **sales category** related to **Procurement category**.

> [!NOTE] 
> If **Create Item Requirement for Procurement Category** is enabled but the **sales categories** aren't linked to the **procurement categories**, the system prevents saving the **purchase order line** and displays an error message.

Once the set up is complete, The system creates item requirements with sales category for each purchase order line created for a procurement category. When the purchase order **product receipt** is posted, the system posts the **item requirements packing slip**, similar to **service items** or **stocked items**, for the purchase packing slip **quantity**.
The system generates the **project cost** financials using the purchase **unit price**, deducting any applicable **purchase discounts**, and also generates the **project posted transactions**.

The system generates **WIP sales** and **accrue revenue** financial transactions if a **sales price** is available on the item requirements generated from the purchase order line.

Learn more about **project purchase orders** in [Project purchase orders](project-purchase-orders.md), and **project purchase product receipts** in [Project cost accrual on purchase receipts](/finance/accounts-payable/project-cost-accrual-purchase-receipts).
