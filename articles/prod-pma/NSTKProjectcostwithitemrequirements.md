---
title: Purchase orders for non-stocked and service items with item requirements
description: Learn how to create purchase orders for non-stocked and service items with item requirements in Dynamics 365 Finance. Follow step-by-step instructions to optimize project costs.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: how-to
ms.date: 01/30/2026
ms.custom: bap-template
---

# Purchase orders for nonstocked and service items with item requirements

To use **Nonstocked** or **Service** items with item requirements, enable the **Enable creation of item requirement for nonstocked items** feature in **Feature management**. These item requirements are automatically created if the parameter for **Create item requirement** is set to **Yes** on the **Financial tab** within Project management and accounting parameters.

1. Go to **Project management & accounting parameters** \> **Setup** \> **Project management and accounting parameters**.
1. On the **General** tab, select **Create item requirement**.

When you create a purchase order line, Microsoft Dynamics 365 Finance generates the project item requirement. Each purchase order line has a direct relationship with a project item requirement. The purchase order line and item requirement link to each other. Any changes to the purchase order directly impact the project item requirement and cause it to update.

If you set the **Item consumption** option to **Yes**, the system automatically posts item requirements when you post a purchase order packing slip. If you set the option to **No**, you receive the following message: "Do you want to consume the material?" You can also manually post the item requirements. Regardless of whether an item requirement is posted manually or automatically, the project cost is generated.

When you post a purchase order invoice, if there's any change in the unit price or a discount, the project cost updates during the vendor invoice posting process, and the project subledger details update accordingly.

## Example scenario

The following example shows a purchase order and project transactions for **Nonstocked** or **Service** items. The purchase order that you create has a net amount of USD 2,000.00. There's a change in the unit price of the vendor invoice to USD 2,500.00.

:::image type="content" source="media/NSTKWithIRPurchaseorder.png" alt-text="Screenshot of purchase order and project transactions.":::

The following illustration shows the project posted transactions that are generated when you post the purchase order product receipt.

:::image type="content" source="media/NSTKWithIRPurchaseProductReceipt.png" alt-text="Screenshot of project posted transactions after product receipt.":::

The following illustration shows the project posted transactions when you post the purchase order vendor invoice. Because there's a change in the unit price, the system posts an adjustment to the existing project posted transactions.

:::image type="content" source="media/NSTKWithIRProjectPostedTransafterVendorInvoice.png" alt-text="Screenshot of project posted transactions after vendor invoice.":::
