---
title: Purchase orders for a project
description: This article describes the various methods that you can use to create purchase orders for a project. The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: article
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

### Methods for creating a purchase order

You can use one of the following methods to create a purchase order in Project management and accounting. The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Method</th>
<th>Purpose</th>
<th>Consumption of items</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Create a purchase order directly from a project.</td>
<td>Use this method to purchase items from an external vendor for consumption on a project. You can create the purchase order in two ways:
<ul>
<li>From the project itself. In this case, the project is already defined for the purchase order.</li>
<li>By navigating to the project purchase order. You must select both the vendor and the project to create the purchase order for.</li>
</ul></td>
<td>Items are consumed when the vendor invoice is updated.</td>
</tr>
<tr class="even">
<td>Create a purchase order from a sales order.</td>
<td>Use this method to purchase items when you create a sales order from a project.</td>
<td>Items are consumed when the sales order is invoiced to the customer.</td>
</tr>
<tr class="odd">
<td>Create a purchase order from an item requirement.</td>
<td>Use this method to purchase items when you create an item requirement from a project.</td>
<td>Items are consumed when the item requirement packing slip is updated.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.

For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).



[!INCLUDE[footer-include](../includes/footer-banner.md)]
