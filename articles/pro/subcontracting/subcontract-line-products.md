---
title: Subcontract lines for products
description: Learn how to create and manage subcontract lines for products in Dynamics 365 Project Operations. Follow step-by-step instructions to streamline vendor purchases.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract lines for products

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A subcontract in Dynamics 365 Project Operations can have a subcontract line for products. By using these lines, a project manager can purchase products from vendors that they can then use on project tasks.

Complete the following steps to create a subcontract line for products in Project Operations.

1. On the navigation page, select **Subcontracts**, and then open the subcontract you want to work with. 
1. On the **Subcontract Lines** tab, select **+ New** to create a new subcontract line.
1. On the **Quick Create** page, in the **Transaction Class** field, select **Material**, and enter or select the required field information. 
1. Select **Save**.

The following table provides information about the fields on the **Subcontract line details** page and the **Quick create** page as they relate to purchasing products.

| Field | Description | Functional impact|
| ----- | ----------- | ----------- |
| Name | Name of the subcontract line to help with identification. |This name appears as the first column in all lookups based on subcontract lines.
| Description | A brief description of products that are being ordered on the subcontract line. | None |
| Line Type | This field has a default value of **Quantity-based**. |None |
| Billing Method | This field is an option set that represents the two main contracting models supported by Project Operations: **Fixed Price** and **Time and Material**. | Based on the billing method you select, a milestone-based invoice schedule is available for subcontract lines with the Fixed Price billing method. |
| Transaction Class |This field has a default value of  **Time**. To create subcontract lines for purchasing products, set the  **Transaction Class**  field to  **Material**.  | This value indicates that the subcontract line is used to record the purchase of products to use on projects. |
| Select Product | Select if the product you're purchasing is maintained in the product catalog or is a write-in  product. |None |
| Product | Select an active product from the catalog. This field is available only when **Select Product** is set to **Existing**. |The combination of **Product** and **Unit** is used as the default or computed for the unit price for the subcontract line.
| Write-In Product | Enter the name of the write-in product. This field is available only when **Select Product** is set to **Write-in**.  |Purchase price isn't automatically filled for write-in products.|
| Requested Delivery Date | Enter the required delivery date for the products.| This date is also used to pick a project price list from the project price lists attached to the subcontract. The cost of the product on the subcontract line then defaults from that price list. |
| Contracted delivery date | Enter the date when the products are contractually agreed to be delivered.  |None|
| Quantity Ordered | Enter the quantity of the product being purchased from the vendor.| This value is used to show warnings when a project manager is over-drawing from this quantity.|
| Unit Group | This value defaults for catalog products only. |When **Product** and **Requested delivery date** are both selected, the system picks the applicable price list based on the delivery date. The related price list items are queried for the matching product. The unit and unit group values default from the setup on the price list item record. |
| Unit | This value defaults to the unit set up on the price list item record. You can change this value to another unit as necessary.| The combination of product and unit is used to default the unit price on the subcontract line for existing catalog products. |
| Unit Price | The unit price defaults by using the combination of product and unit from the price list items related to the project price list that's applicable for the requested delivery date of the subcontract line.  |None |
| Subtotal | This read-only field is calculated as Quantity x Unit price if both fields have values entered. If either the **Quantity** field, **Unit price** field, or both are empty, you can enter a value manually.  |None |
| Sales Tax | Enter the sales tax value. |None |
| Total Amount | This calculated field shows the total amount of the subcontract line after including taxes. The value in this field is calculated as Subtotal + Tax. |None |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
