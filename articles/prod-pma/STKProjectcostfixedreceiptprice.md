---
title: Purchase orders for stocked items with fixed price
description: Learn how to manage purchase orders for stocked items with fixed prices. Discover how to set up fixed receipt pricing and handle cost variances effectively.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: how-to
ms.custom: 
  - bap-template
ms.date: 02/06/2026
---

# Purchase orders for stocked items with fixed price

[!include [banner](../includes/banner.md)]

To use the **Fixed receipt price** option for project costing, set the **Fixed receipt price** option to **Yes** for the item model group.

1. Go to **Inventory management** \> **Setup** \> **Inventory** \> **Item model group**.
1. Set the **Fixed receipt price** option to **Yes**.

This feature works like a standard cost where all the receipts and consumption use the cost price that you define for the item.

If a purchase has a unit price that's higher or lower than the cost price you defined for the item, the system posts the variance to the purchase fixed receipt price profit or loss account and the fixed receipt price offset account. Because of this variance, the system always maintains the item cost price like the standard cost price for the product.

For project item consumption, the project cost always updates with the item cost price, regardless of whether the consumption is done through item requirements or purchase orders that have item requirements.

If there's a change in the fixed cost price, run the **Inventory closing** process, adjust the on-hand inventory, and then activate the new cost.

## Example scenario

The following example shows the project cost for items where you set the **Fixed price** option to **Yes** for the item model group.

The following illustration shows the purchase order and vendor invoice that you post for the purchase order.

:::image type="content" source="media/STKFixedreceiptpricePO.png" alt-text="Screenshot of purchase order and vendor invoice.":::

The following illustration shows the project posted transaction where the project cost is posted as USD 100.00.

:::image type="content" source="media/STKFixedreceiptpricePostedTransactions.png" alt-text="Screenshot of project posted transactions.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
