---
title: Use procurement categories with project purchase orders and pending vendor invoices
description: This describes how to configure procurement categories to be used with project purchase orders and pending vendor invoices
author: sigitac
ms.date: 04/07/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# Use procurement categories with project purchase orders and pending vendor invoices

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Purchasing professionals can create and maintain catalogs of the items and services that can be used in **Project purchase orders** and **Pending vendor invoices**.
[Procurement catalogs](/supply-chain/procurement/procurement-catalogs) provide an easy way to categorize purchases without a need to configure and use a released products catalog. Each **Procurement category** can be mapped to a **Project category** for time, expense or item transactions.
After a pending vendor invoice that uses a procurement category is posted, the system will create time, expense or material project actuals, project transactions and subledger entries.

## Minimum version requirement

Using **Procurement categories** with **Project purchase orders** for Dynamics 365 Project Operations non-stocked/resource based scenarios requires the following versions:
- Project Operations Dataverse solution – 4.41.0.45 or higher
- Finance and Operations environment version - 10.0.26 or higher

## Run Dual-write maps for procurement categories support

Ensure the mapping for **Project Operations integration project vendor invoice line export entity msdyn_projectvendorinvoicelines** is using 1.0.0.4 or higher version.

## Enable the feature key for Procurement categories

Complete the following steps to enable functionality to use procurement categories with project purchase orders.

1. In Dynamics 365 Finance, go to the **Feature management** workspace.
1. In the feature list, find the **Use procurement categories in Project Operations for resource based/non-stocked scenarios** feature, and then select **Enable**.

> [!NOTE]
> As a prerequisite, you must also enable the feature **Enable pending vendor invoices on Project Operations for resource based/non-stocked scenarios**.

## Map Project categories in Procurement category hierarchy

Complete the following steps to map **Project categories** to **Procurement categories** in the **Procurement category** hierarchy:

1. Go to **navigation pane > Modules > Procurement and sourcing > Procurement categories**.
1. Select **Edit category hierarchy**.
1. Select the desired category hierarchy node, and then in the **Assign project categories** tab, associate the node with the Project category from the Time, Expense or Item Project category (i.e. Default-Time or Default-Expense categories).
1. Select **Save**.
1. Close the page.

> [!NOTE]
> Mapping a **Procurement category** to **Project category** is optional. If **Procurement category** is not mapped, the system will use the value set in the **Project Management and Accounting parameters > Project Operations on Dynamics 365 Customer engagement > Project category defaults > Item**.

