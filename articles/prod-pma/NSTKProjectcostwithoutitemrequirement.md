---
title: Purchase orders for Non-stocked/service items without item requirements
description: This article provides information about project purchase orders for Non-stock/service items without item requirements.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: article
ms.date: 2/21/2023
ms.custom:
---

# Purchase order for Non-stock/Service items without item requirements

To use this feature, the **Item requirements** parameter in the **Project management & accounting parameters** must be set to **No**.

**Project management and accounting** \> **Setup** \> **Project management & accounting parameters** \> **General** \> **Create Item requirements** : **No**

When a purchase order is created without using the item requirements feature, **Dynamics 365 Finance** generates & posts the project cost at time of vendor invoice. When the **Purchase order** product receipt is posted, no project cost transactions are generated.

**Dynamics 365 Finance** considers the purchase unit price, discount and Miscellaneous charges assigned to the vendor invoice as project cost. If the Miscellaneous charges are configured as loaded on inventory (Debit, inventory) then Miscellaneous charge amount is added to the unit cost and discount and project cost is generated accordingly.

## Example scenario

The following example shows the **Purchase order** and **Project transactions** for the **Non-stocked** or **Service** items. Purchase order is created with **Net amount** USD 2,700.00 after discount. Miscellaneous charges of USD 100.00 added on the purchase order line ( **Item, Debit** ).
![image](https://user-images.githubusercontent.com/103096040/220301641-f17887ad-8aa4-4e0e-a7dc-55ad5ab17f6b.png)


The following screen shows the project cost USD2,800.00 and **Project subledger** generated for purchase order when vendor invoice is posted. 
![image](https://user-images.githubusercontent.com/103096040/220301766-9137d971-5d98-4e7b-bcf2-c30653bff97a.png)

