--- 
title: Receive items on purchase order from item requirement
description: This article explains how to receive items on a purchase order from an item requirement. 
author: Yowelle
ms.date: 08/06/2019
ms.topic: how-to 
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines   
audience: Application User 
ms.reviewer: johnmichalak
ms.search.region: Global
ms.author: andchoi
ms.search.validFrom: 2016-06-30 
ms.dyn365.ops.version: Version 7.0.0 
---
# Receive items on purchase order from item requirement

[!include [banner](../../includes/banner.md)]

This article explains how to receive items on a purchase order from an item requirement.

By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning. 

This task uses the USSI data set.

1. In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.
2. In the list, select the link in the desired row.
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
15. In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.
16. In the list, select the link in the desired row.
17. On the Action Pane, select **Purchase**.
18. Select **Confirm**.
19. On the Action Pane, select **Receive**.
20. Select **Product receipt**.
21. In the **Product receipt** field, type a value.
22. Select **OK**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
