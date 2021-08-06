---
title: Subcontract lines for products
description: This topic explains how to record subcontract lines for products and use the various fields to record product purchases from vendors.
author: rumant
ms.date: 08/06/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract lines for products

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Dynamics 365 Project Operations can have subcontract line for products. These lines allow a Project Manager to purchase products from vendors that they can then use on project tasks.

Complete the following steps to create a subcontract line for products in Project Operations.

1. On the navigation page, select **Subcontracts**, and then open the subcontract you want to work with. 
2. On the **Subcontract Lines** tab, select **+ New** to create a new subcontract line.
3. On the **Quick Create**, in the **Transaction Class** field, select **Material** and enter or select the required field information. 
4. Select **Save**.

The following table provides information about the fields on the Subcontract line details page and the quick create page as they are relevant for purchasing products.

| Field | Description |
| ----- | ----------- |
| Name | The name of the subcontract line. |
| Description | A brief description of products that are being ordered on the subcontract line. |
| Line Type | This field value defaults to **Quantity-based**. |
| Billing Method |  The billing method of the subcontract line. A milestone-based invoice schedule is available for fixed-price billing methods. |
| Transaction Class | This field value defaults to **Time**. To create subcontract lines for purchasing products, in the **Transaction Class** field select **Material**. This selection indicates that the subcontract line is used to record a purchase of products to be used on projects. |
| Select Product | Select if the product being purchased is maintained in the product catalog or is a write-in  product. |
| Product | Select an active product from the catalog. This field is available only when **Select Product** is set to **Existing**. |
| Write-In Product | Enter the name of the write-in product. This field is available only when **Select Product** is set to **Write-in**.  |
| Requested Delivery Date | Select the required deliver date for the products. This date is also used to pick a project price list from the project price lists attached to the subcontract. The cost of the product on the subcontract line then defaults from that price list. |
| Contracted delivery date | Select the date when the products are contractually agreed to be delivered.  |
| Quantity Ordered | Enter te quantity of the product being purchased from the vendor. If a Project Manager overdraws from this quantity, a warning will occur. |
| Unit Group | This value defaults for catalog products only. When **Product** and **Requested delivery date** are both selected, the system picks the applicable price list based on the delivery date. The related price list items are queried for the matching product. The unit and unit group values default from the setup on the price list item record. |
| Unit | This value defaults to the unit setup on the price list item record. You can change this to another unit as necessary. The combination of product and unit is used to default the unit price on the subcontract line for existing catalog products. |
| Unit Price | The unit price defaults by using the combination of product and unit from the price list items related to the project price list that is applicable for the requested delivery date of the subcontract line.  |
| Subtotal | This read-only field is calculated as Quantity x Unit price if both fields have values entered. If either the **Quantity** field, **Unit price** field, or both are empty, you can enter a value manually.  |
| Sales Tax | Enter the sales tax value. |
| Total Amount | This calculated field shows the total amount of the subcontract line after including taxes. The value in this field is calculated as subtotal + tax. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
