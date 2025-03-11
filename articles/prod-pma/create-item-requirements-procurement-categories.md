---
title: Manage project production orders
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

### Minimum versions required

To use the feature for Dynamics 365 Project Operations for stocked based scenario, you must have the following versions:

- Finance version 10.0.44 or later

## Setup project management and accounting parameters

Follow these steps to enable the item requirements feature for project purchase order lines created for procurement categories.

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
2. Go to **General** tab.
3. Mark **Create item requirement** to **yes**.
4. Mark **Create item requirement for procurement category** to **yes**.

> [!NOTE] 
> **Create Item requirement for procurement category** will be enabled for selection only after selecting the **Create Item Requirements** option. If this option is not selected, then item requirement lines will not be created for the project purchase order lines.

## Set up default sales categories for the procurement categories

To use the **item requirements** feature for **procurement categories**, you need to establish a relationship between the **procurement category** and the **sales category**, as item requirements only support sales categories.

1. Go to **Procurement and sourcing** > **Procurement categories**.
2. On the action pane, click **Edit procurement hierarchy**.
3. On the **Assign procurement categories** tab, select **sales category** related to **procurement category**.

> [!NOTE] 
> If **Create Item Requirement for Procurement Category** is enabled but sales categories are not linked to procurement categories, the system will prevent saving the purchase order line and display an error message.

Once the above setup is completed, the system will automatically create **item requirements** with **sales category** for each **purchase order line** created for a **procurement category**. When the purchase order **product receipt** is posted, 
the system will automatically post the **item requirements packing slip**, similar to **service items** or **stocked items**, for the purchase packing slip **quantity**. The system will generate the **project cost** financials using the purchase **unit price**, 
deducting any applicable **purchase discounts**, and will also generate the **project posted transactions**.

The system will also generate **WIP sales** and **accrue revenue** financial transactions if a **sales price** is available on the item requirements generated from the purchase order line.

For more information about **project purchase order**, refer [Project purchase orders](articles/prod-pma/project-purchase-orders.md) and for **project purchase product receipt**, refer [Project cost accrual on purchase receipts](/articles/finance/accounts-payable/project-cost-accrual-purchase-receipts.md).
