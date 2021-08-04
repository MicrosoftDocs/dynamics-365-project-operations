---
title: Subcontract lines for products
description: This topic provides information that will help you record Subcontract lines for Products and how to use the various fields to record the purchase of products from vendors for use on projects and project tasks.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract lines for products

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Project Operations can have Subcontract line for products. Subcontract lines for products allow a project manager to purchase products from vendors that they can, then, use / consume on Project tasks.

To create a subcontract line for products in Project Operations, follow these steps:

- Open a Subcontract and navigate to Subcontract Lines tab.
- On the Subcontract Line tan select + New to create a new Subcontract Line
- On the Quick Create for Subcontract Line, make sure to select Transaction Class as &#39;Material&#39;, fill in the required fields and Save the subcontract line.

The following table provides information about the fields on the Subcontract line details page and the quick create page as they are relevant for purchasing products.

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Name | Quick Create page and General tab of the Subcontract line details page | Name of the subcontract line to help with identification | This will be shown as the first column in all look ups based on Subcontract lines |
| Description | Quick Create page and General tab of the Subcontract line details page | Description of products that are being ordered/purchased on the Subcontract line | |
| Line Type | Quick Create page and General tab of the Subcontract line details page | Defaulted to &#39;Quantity-based&#39;* | |
| Billing Method | Quick Create page and General tab of the Subcontract line details page | This is an option set that represents the two main contracting models supported by Project Operations: <br> -  **Fixed Price**<br> -  **Time and Material** | Based on the billing method of the referenced subcontract line, a milestone – based invoice schedule is made available for Fixed Price billing method. |
| Transaction Class | Quick Create page and General tab of the Subcontract line details page | Defaulted to Time. For creating Subcontract Lines for purchasing products, set the Transaction Class to &#39;Material&#39;. | This indicates that the subcontract line is being used to record a purchase of products or materials to be used on projects |
| Select Product | Quick Create page and General tab of the Subcontract line details page | Should be used to define if the product being purchased is maintained in the product catalog or is going to be a write – in. Supported choices are:<br>- Existing<br>- Write In | Selecting &#39;Existing&#39; would indicate that the product being purchased is maintained in the product catalog.Selecting &#39;Write in&#39; would indicate that the product being purchased is not in the catalog. |
| Product | Quick Create page and General tab of the Subcontract line details page | Shows a dropdown list of active products in the catalog. This field is shown only when **Select**** Product** is set to &#39;Existing&#39; | |
| Write In Product | Quick Create page and General tab of the Subcontract line details page | Allows the user to type in the name of the write-in product. This field is shown only when **Select**** Product** is set to &#39;Write in&#39; | |
| Requested Delivery Date | Quick Create page and General tab of the Subcontract line details page | Date when the products are required to be delivered | Requested delivery date is also used to pick a project price list from the project price lists attached to the subcontract. Cost of the product on the subcontract line is then defaulted from that price list |
| Contracted delivery date | Quick Create page and General tab of the Subcontract line details page | Date when the products are contractually agreed to be delivered | |
| Quantity Ordered | Quick Create page and General tab of the Subcontract line details page | Quantity of the product being purchased from the vendor | This will be used to show warnings when a project manager is over-drawing from this quantity of the product being purchased |
| Unit Group | Quick Create page and General tab of the Subcontract line details page | Defaulted for catalog products only. When Product and Requested delivery date are both selected. Based on the delivery date, the system picks the applicable price list and related price list items are queried for the matching product. Unit and unit group values are defaulted from the setup on the price list item record. | |
| Unit | Quick Create page and General tab of the Subcontract line details page | Defaulted to the unit setup on the price list item record. User may change this to any other unit | The combination of product and Unit will be used to default the unit price on the Subcontract line for existing catalog products. |
| Unit Price | Quick Create page and General tab of the Subcontract line details page | Unit price is defaulted using the combination of Product and Unit from the price list items related to the project price list applicable for the Requested Delivery Date of the Subcontract line | |
| Subtotal | Quick Create page and General tab of the Subcontract line details page | Read only field that is automatically computed as Quantity * Unit price if both Quantity and Unit price values are entered. If either quantity or unit price or both are left empty, then this field is available for entering a value. | |
| Sales Tax | Quick Create page and General tab of the Subcontract line details page | Editable field that is available for the user to enter a value. | |
| Total Amount | Quick Create page and General tab of the Subcontract line details page | This is a calculated field that is denotes the total amount of the subcontract line after including taxes. Calculated as Subtotal +Tax | |

*See Subcontracting in Project Operations - Early Access Scope

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
