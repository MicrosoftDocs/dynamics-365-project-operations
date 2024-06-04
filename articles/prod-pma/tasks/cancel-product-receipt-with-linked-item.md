---
title: Cancel a purchase order product receipt with a linked item requirement
description: This article explains how to cancel a project purchase order that has a linked item requirement.
author: nimaski
ms.author: nimaski
ms.date: 06/04/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Cancel a purchase order product receipt with a linked item requirement

[!include [banner](../../includes/banner.md)]

This article explains how to cancel a project purchase order that has a connected (linked) item requirement.

## New feature to enable cancellation

The version 10.0.37 release lets you cancel product receipts that have a linked item requirement. You must first enable the prerequisite **Enable packing slip cancellation for item requirements** feature. This feature changes the posting behavior for newly created stocked item requirements. After that feature is enabled, you can enable the **Enable purchase order product receipt cancellation with linked item requirements** feature. This feature extends the posting changes to item requirements that are linked to purchase orders.

> [!NOTE]
> These features don't affect existing item requirements if the packing slip was previously posted for them. Only new item requirements and existing item requirements that no packing slip has been posted for use the new posting behavior.

The **Enable purchase order product receipt cancellation with linked item requirements** feature adds two new fields to the **Project** tab of the **Purchase Order** page. The **Quantity** field in **Line details** shows the item requirement quantity and provides drill-down to the **Item requirement** page. The **Deliver remainder** field shows the remaining quantity on the item requirement.

## Cancel a product receipt that has a linked item requirement

This procedure uses the USSI data set. To cancel a product receipt that has a linked item requirement, follow these steps.

1. Go to **Project management and accounting** \> **Projects** \> **All projects**.
1. In the list, select the project.
1. On the Action Pane, select **Plan**.
1. Select **Item requirements**.
1. Select **New**.
1. On the new row, in the **Item number** field, enter or select a value.
1. In the **Quantity** field, enter a number.
1. Select **Save**.
1. On the Action Pane, select **Manage**.
1. Select **Functions**.
1. Select **Create purchase order**.
1. Select the **Include all** checkbox.
1. In the **Vendor account** field, enter or select a value.
1. Select **OK**.
1. Use the navigation pane to go back to the selected project.
1. On the Action Pane, select **Manage**.
1. Under the related information, select **Item tasks**, and then select **Purchase orders**.
1. Open the newly created purchase order.
1. On the Action Pane, select **Purchase**.
1. Select **Confirm**.
1. On the Action Pane, select **Receive**.
1. Select **Product receipt**.
1. In the **Product receipt** field, enter a value.
1. Select **OK**.
1. If you receive a message that prompts you to consume items for the project immediately, select **Yes**. The packing slip for the item requirement is then posted.
1. After the purchase order is received and the item requirement is delivered, cancel both documents in reverse order. From the purchase order, tap (or click) in the **Project** field in **Line details**, and select the link under the **Item requirement** header for the linked **Quantity** value.
1. On the **Item requirements** page, select **Manage**.
1. Select **Inquiries**.
1. Select **Packing slip journal**
1. On the Action Pane, select **Cancel**.
1. On the **Other** tab of the item requirement, tap (or click) in the **Reference number** field to open the linked purchase order.
1. On the Action Pane of the purchase order, select **Receive**.
1. Select **Product receipt**.
1. Select **Cancel**.
1. You receive the following message: "This will cancel the receipt of all lines on this packing slip. Do you want to continue?" Select **Yes** to complete the cancellation of the product receipt.

> [!NOTE]
> Regardless of whether the item is a **stocked**, **non-stocked**, or **service** item, the line status for the item requirement is **Delivered** when the packing slip is posted.

The reversal resolves any used inventory and reverses any financial postings.

#### Demo data issues to consider

In the **USSI** legal entity, the **Sale\_367** number sequence is in an inconsistent state. Cancellation of an item requirement causes an error. Here's an example of the error message that you receive:

> Voucher 000001 is already used as of date 1/9/2017. Posting has been cancelled.

To fix the issue, go to **Number sequences**, filter for number sequence code **Sale\_367**, and open the item. On the **Performance** FastTab, change the value of the **Preallocation** option from **Yes** to **No**, and save the change. Then change the value back to **Yes**.
