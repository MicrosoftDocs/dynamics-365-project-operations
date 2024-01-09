---
# required metadata 

title: Cancel a purchase order product receipt with linked item requirement
description: This article explains how to cancel a project purchase order with a connected item requirement
author: ryansandness
ms.date: 01/04/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.prod:  
ms.technology:  

# optional metadata

ms.search.form:
audience: Application User 
# ms.devlang:  
ms.reviewer: johnmichalak

# ms.tgt_pltfrm:  
# ms.custom:  
ms.search.region: Global
ms.search.industry: Service industries
ms.author: ryansandness
ms.search.validFrom: 2016-06-30 
ms.dyn365.ops.version: Version 7.0.0
---

# Cancel a purchase order product receipt with linked item requirement

[!include [banner](../../includes/banner.md)]

This article explains how to cancel a project purchase order with a connected item requirement.

## New feature available to enable cancellation

The version 10.0.37 release enables the cancellation of a product receipt with a linked item requirement. The prerequisite feature **Enable packing slip cancellation for item requirements** must be first enabled, and then the **Enable purchase order product receipt cancellation with linked item requirements** feature can be enabled.

The first feature, **Enable packing slip cancellation for item requirements**, changes the posting behavior for newly created stocked item requirements. The second feature, **Enable purchase order product receipt cancellation with linked item requirements**, extends the posting changes to item requirements connected to purchase orders.

> [!NOTE]
> Existing item requirements are not affected by these features if they previously had the packing slip posted. Only new item requirements or item requirements with no packing slip posted use the new posting behavior.

The **Enable purchase order product receipt cancellation with linked item requirements** feature adds two new fields onto the **Project** tab of the **Purchase Order**. **Line details** provides the item requirement **Quantity** which drills down to the **Item requirement** form, and the **Deliver remainder** provides the remaining quantity on the item requirement.

## Cancelling a product receipt with a linked item requirement

This task uses the USSI data set. To cancel a product receipt with a linked item requirement, follow these steps.

1. In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.
2. In the list, select the project.
3. On the Action Pane, select **Plan**.
4. Select **Item requirements**.
5. Select **New**.
6. In the new row, enter or select a value in the **Item number** field.
7. In the **Quantity** field, enter a number.
8. Select **Save**.
9. On the Action Pane, select **Manage**.
10. Select **Functions**.
11. Select **Create purchase order**.
12. Select the **Include all** check box.
13. In the **Vendor account** field, enter or select a value.
14. Select **OK**.
15. In the navigation pane, go back to the selected project.
16. On the Action Pane, select **Manage**.
17. Under related information, select **Item tasks** and then select **Purchase orders**.
18. Open the newly created purchase order.
19. On the Action Pane, select **Purchase**.
20. Select **Confirm**.
21. On the Action Pane, select **Receive**.
22. Select **Product receipt**.
23. In the **Product receipt** field, type a value.
24. Select **OK**.
25. If prompted to **Consume items for the project immediately**, select **Yes**. Selecting yes posts the packing slip for the item requirement.
26. With the PO received and the item requirement delivered, cancel both documents in reverse order. From the purchase order, click into the **Project** on the **Line details** and select the link under the **Item requirement** header for the linked **Quantity**.
27. In the **Item requirements** form, select **Manage**.
28. Select **Inquiries**.
29. Select **Packing slip journal**
30. On the Action Pane, select **Cancel**.
31. On the **Other** tab of the item requirement, click into the **Reference number** to open the linked purchase order.
32. On the Action Pane of the purchase order, select **Receive**.
33. Select **Product receipt**.
34. Click **Cancel**.
35. A prompt appears with a message stating that **This will cancel the receipt of all lines on this packing slip. Do you want to continue?** Select **Yes** to complete the cancellation of the **Product receipt**.

> [!NOTE]
> Note: Whether the item is a **stocked**, **non-stocked** or **service** item, the line status for the item requirement is **Delivered** when posting the **packing slip**.

The reversal resolves any used inventory and reverses any financial postings.

#### Demo data issues to consider

In the **USSI** legal entity, the **Sale\_367** number sequence is in an inconsistent state. Cancellation of an item requirement causes the following error:

> Voucher 000001 is already used as of date 1/9/2017. Posting has been cancelled.

To fix the issue, go to **Number sequences**, filter for number sequence code **Sale\_367**, and open the item. On the **Performance** FastTab, change the value of the **Preallocation** option from **Yes** to **No**, and save the change. Then, change the value back to **Yes**.
