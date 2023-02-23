---
title: Purchase orders for stocked items with fixed price.
description: This article provides information about project purchase orders for stocked items with fixed price.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: article
ms.date: 2/21/2023
ms.custom:
---
# Purchase orders for stocked items - Fixed receipt price 

To use **Fixed receipt price** parameter in the **Inventory model group**, enable the **Item requirements** parameter using these steps.

1. From **Inventory management**, select **Setup**, **Inventory**, and **Item model group**.
1. Set **Item model group** to **Yes**.

This feature works like a standard cost where all the receipts and consumption happens on the cost price defined for the item.

When there is a purchase with a unit price that is more or less than the cost price defined for the item, the system posts the variance into purchase fixed receipt price profit or loss account and fixed receipt price offset account. Because of this, the system always maintains the item cost price like the standard cost price for the product.

For project item consumption, either through **Item requirements** or **Purchase orders** with **Item requirements** , project cost is always updated with the item cost price.

When there is a change in the fixed cost price, need to run the **Inventory closing** , adjust the on-hand inventory, and then activate the new cost.

## Example scenario

The following example shows the project cost for the items with **Fixed price** set to **Yes** on the **Item model group**.

The following screen shows the purchase order and vendor invoice posted for the purchase order.

![Screenshot of purchase order](media/STKFixedreceiptpricePO.png)

The following screen shows the Project posted transaction with project cost posted as USD 100.00.

![Screenshot of project posted transactions](media/STKFixedreceiptpricePostedTransactions.png)
