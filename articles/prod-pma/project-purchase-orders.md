---
title: Purchase orders for a project
description: Learn how to create purchase orders for projects using different methods based on their purpose and consumption timing. Optimize your project management process today.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.search.form: ProjTable 
audience: Application User
ms.reviewer: johnmichalak
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0

---

# Purchase orders for a project

[!include [banner](../includes/banner.md)]

This article describes the various methods that you can use to create purchase orders for a project. The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.

## Methods for creating a purchase order

You can use one of the following methods to create a purchase order in Project management and accounting. The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.

| Method | Purpose | Consumption of items |
|--------|---------|----------------------|
| Create a purchase order directly from a project. | Use this method to purchase items from an external vendor for consumption on a project. You can create the purchase order in two ways: From the project itself. In this case, the project is already defined for the purchase order. By navigating to the project purchase order. You must select both the vendor and the project to create the purchase order for. | Items are consumed when the vendor invoice is updated. |
| Create a purchase order from a sales order. | Use this method to purchase items when you create a sales order from a project. | Items are consumed when the sales order is invoiced to the customer. |
| Create a purchase order from an item requirement. | Use this method to purchase items when you create an item requirement from a project. | Items are consumed when the item requirement packing slip is updated. |

> [!NOTE]
> When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.

For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
