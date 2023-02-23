---
title: Inventory consumption for projects.
description: This article provides information about inventory consumption for projects.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: article
ms.date: 2/21/2023
ms.custom:
---

# Inventory consumption from stock

**Microsoft Dynamics 365 Finance** allows inventory consuming from the warehouse using Project **Item requirements** and **Project item journal**. ** Microsoft Dynamics 365 Finance** always considers the **Weighted average** costing method for item requirements, except for standard costing. Whenever a new item requirement is posted, irrespective of the item model group mapped on the product, the default **Weighted average** costing method is applied, and the same is reflected on the Project posted transactions.

This is in line with the sales orders without projects where actual cost consumption is updated after the inventory recalculation and costing.

After the **Inventory recalculation** process, the system calculates the actual cost based upon the inventory model that is mapped to the item and adjusts the inventory cost for the project as well.

## Example scenario

The following examples show the project cost transactions that are posted with item requirements for items that have different **Inventory costing** methods applied to the items.

**Inventory costing method: FIFO**

The following example shows the project cost transactions posted for **Item requirements** for an item with **FIFO** inventory costing method.

| **Transaction type** | **Item id** | **Qty** | **Unit price** | **Total Amount** | **Item cost price** | **After Recalculation** |
| --- | --- | --- | --- | --- | --- | --- |
| Purchase order without Project | F001 | 100.00 | 200.00 | 20,000.00 |   |   |
| Purchase order without Project | F001 | 100.00 | 200.00 | 20,000.00 |   |   |
| Purchase order without Project | F001 | 100.00 | 1,000.00 | 100,000.00 |   |   |
| Item requirements or Project item journal | F001 | (1.00) | 200.00 | (200.00) | 466.67 | 200.00 |

The following screen shows the project posted transactions generated after the **Item requirements** packing slip posting process.

![Screenshot of project posted transactions voucher](media/STKIRVoucher.png)

The following screen shows the project posted transactions generated after the **Inventory recalculation** process. The system has generated adjustment vouchers for the transactions generated for **Item requirements.**

![Screenshot of project posted transactions after inventory recalculation process](media/STKIRVoucherafterAdjustment.png)

**Inventory costing method: Weighted average**

The following example shows the project cost transactions posted for **Item requirements** for an item with **Weighted average** inventory costing method.

| **Transaction type** | **Item id** | **Qty** | **Unit price** | **Total Amount** | **Item cost price** | **After Recalculation** |
| --- | --- | --- | --- | --- | --- | --- |
| Purchase order without Project | W001 | 100.00 | 100.00 | 10,000.00 |   |   |
| Purchase order without Project | W001 | 100.00 | 300.00 | 30,000.00 |   |   |
| Purchase order without Project | W001 | 100.00 | 3,000.00 | 300,000.00 |   |   |
| Item requirements | W001 | (1.00) | 300.00 | (300.00) | 1133.33 | 1133.33 |

The following screen shows the project posted transactions generated after the **Item requirements** posting process.

![Screenshot of project posted transactions](media/STKIRVoucherWAvg.png)
