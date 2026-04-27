---
title: Purchase orders for non-stocked and service items without item requirements
description: Learn how to create purchase orders for non-stocked and service items without item requirements in Dynamics 365 Finance. Follow step-by-step instructions to optimize project costs.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: how-to
ms.date: 01/30/2026
ms.custom: bap-template
---

# Purchase orders for non-stocked and service items without item requirements

[!include [banner](../includes/banner.md)]

To use purchase orders without item requirements, set the **Create Item requirements** option to **No** in Project management & accounting parameters.

1. Go to **Project management and accounting** \> **Setup** \> **Project management & accounting parameters**.
1. On the **General** tab, set the **Create Item requirements** option to **No**.

When you create a purchase order without using the **Item requirements** feature, Microsoft Dynamics 365 Finance generates and posts the project cost at the time of vendor invoice posting. When you post the purchase order product receipt, no project cost transactions are generated.

Dynamics 365 Finance considers the purchase unit price, discount, and miscellaneous charges that you assign to the vendor invoice as the project cost. If you configure the miscellaneous charges as loaded on inventory (that is, if they're charges of the **Debit, inventory** type), the miscellaneous charge amount is added to the unit cost and discount, and the project cost is generated accordingly.

## Example scenario

The following example shows a purchase order and project transactions for **Non-stocked** or **Service** items. The purchase order that you create has a net amount of USD 2,700.00 after you apply discounts. You add miscellaneous charges of USD 100.00 on the purchase order line (Miscellaneous charge of **Item, Debit** type).

:::image type="content" source="media/NSTKWithoutIRPurchaseOrder.png" alt-text="Screenshot of the purchase order and project transactions.":::

The following illustration shows the project cost of USD 2,800.00 and the project subledger that's generated for the purchase order when you post the vendor invoice.

:::image type="content" source="media/NSTKWithoutIRProjectPostedTransactions.png" alt-text="Screenshot of project posted transactions and the project subledger.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
