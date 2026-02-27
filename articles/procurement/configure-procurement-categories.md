---
title: Use procurement categories with project purchase orders and pending vendor invoices
description: This article describes how to configure procurement categories that can be used with project purchase orders and pending vendor invoices.
author: mukumarm
ms.author: mukumarm
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak 

---

# Use procurement categories with project purchase orders and pending vendor invoices

_**Applies To:** Project Operations Integrated with ERP_

Purchasing professionals can create and maintain catalogs of the items and services that can be used in project purchase orders and pending vendor invoices. [Procurement catalogs](/dynamics365/supply-chain/procurement/procurement-catalogs) give you an easy way to categorize purchases without having to configure and use a released products catalog. You can map each procurement category to a project category for time, expense, or item transactions. After you post a pending vendor invoice that uses a procurement category, the system creates time, expense, or material project actuals, project transactions, and subledger entries.

## Minimum version requirements

To use procurement categories with project purchase orders for Microsoft Dynamics 365 Project Operations non-stocked and resource-based scenarios, you need the following versions:

- Project Operations Dataverse solution version 4.41.0.45 or later
- Finance and operations environment version 10.0.26 or later

## Run dual-write maps for procurement category support

Make sure that the mapping for **Project Operations integration project vendor invoice line export entity msdyn\_projectvendorinvoicelines** uses version 1.0.0.4 or later.

## Enable the feature key for procurement categories

Enable the functionality for using procurement categories with project purchase orders.

1. In Dynamics 365 Finance, open the **Feature management** workspace.
1. In the feature list, find the **Use procurement categories in Project Operations for resource based/non-stocked scenarios** feature, and then select **Enable**.

> [!IMPORTANT]
> As a prerequisite, you must also enable the **Enable pending vendor invoices on Project Operations for resource based/non-stocked scenarios** feature.

## Map project categories in the Procurement category hierarchy

Follow these steps to map project categories to procurement categories in the **Procurement category** hierarchy:

1. Go to **Procurement and sourcing > Procurement categories**.
1. Select **Edit category hierarchy**.
1. Select the category hierarchy node that you want. On the **Assign project categories** tab, associate the node with the project category from the **Time**, **Expense**, or **Item Project** category. This category can be the **Default-Time** or **Default-Expense** category.
1. Select **Save**.
1. Close the page.

> [!NOTE]
> You don't need to map a procurement category to a project category. If you don't map a procurement category, the system uses the value that you set in the **Item** field in the **Project category defaults** section on the **Project Operations on Dynamics 365 Customer engagement** tab of the **Project management and accounting parameters** page.

[!INCLUDE[footer-include](../includes/footer-banner.md)]