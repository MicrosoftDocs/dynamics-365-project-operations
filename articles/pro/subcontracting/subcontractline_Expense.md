---
title:  Subcontract lines for Expense Categories
description: This topic provides information that will help you record Subcontract lines for Expense and how to use the various fields to record the purchase of time from vendors.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

#  Subcontract lines for Expense Categories

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Project Operations can have Subcontract line for expense categories. Subcontract lines for expense categories allow a project manager to purchase categories of services or products from vendors that they can, then, charge to project.

To create a subcontract line for categories of expenses in Project Operations, follow these steps:

- Open a Subcontract and navigate to Subcontract Lines tab.
- On the Subcontract Line tan select + New to create a new Subcontract Line
- On the Quick Create for Subcontract Line, make sure to select Transaction Class as &#39;Expense&#39;, fill in the required fields and Save the subcontract line.

The following table provides information about the fields on the Subcontract line details page and the quick create page as they are relevant for purchasing expense categories.

| **Field** | **Location** | **Relevance, purpose, and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Name | Quick Create page and General tab of the Subcontract line details page | Name of the subcontract line to help with identification | This will be shown as the first column in all look ups based on Subcontract lines |
| Description | Quick Create page and General tab of the Subcontract line details page | Description of categories of service or products that are being ordered/purchased on the Subcontract line | |
| Line Type | Quick Create page and General tab of the Subcontract line details page | Defaulted to &#39;Quantity-based&#39;* | |
| Billing Method | Quick Create page and General tab of the Subcontract line details page | This is an option set that represents the two main contracting models supported by Project Operations: <br> -  **Fixed Price** <br> -  **Time and Material** | Based on the billing method of the referenced subcontract line, a milestone – based invoice schedule is made available for Fixed Price billing method. |
| Transaction Class | Quick Create page and General tab of the Subcontract line details page | Defaulted to Time. For creating Subcontract Lines for purchasing products, set the Transaction Class to &#39;Expense&#39;. | This indicates that the subcontract line is being used to record a purchase of a category of products or services to be used on projects |
| Transaction Category | Quick Create page and General tab of the Subcontract line details page | Shows a dropdown list of active transaction categories setup in the system. | |
| Requested Start | Quick Create page and General tab of the Subcontract line details page | Date when the categories of purchase are required to be available from the vendor | Requested start is used to pick a project price list from the project price lists attached to the subcontract. Cost of the category on the subcontract line is then defaulted from that price list |
| Requested end | Quick Create page and General tab of the Subcontract line details page | Date when the categories of purchase would no longer be needed | This will be used to show warnings when a project manager is associating this subcontract line to specific expense estimates on the project that are dated after this end date. |
| Quantity Ordered | Quick Create page and General tab of the Subcontract line details page | Quantity of the category being purchased from the vendor | This will be used to show warnings when a project manager is over-drawing from this quantity being purchased |
| Unit Group | Quick Create page and General tab of the Subcontract line details page | Defaulted based on the Default unit group setup for the selected category | |
| Unit | Quick Create page and General tab of the Subcontract line details page | Defaulted based on the Default unit setup for the selected category | The combination of Category and Unit will be used to default the unit price on the Subcontract line. |
| Unit Price | Quick Create page and General tab of the Subcontract line details page | Unit price is defaulted using the combination of Category and Unit from the Category prices related to the project price list applicable for the Requested start of the Subcontract line | |
| Subtotal | Quick Create page and General tab of the Subcontract line details page | Read only field that is automatically computed as Quantity* Unit price if both Quantity and Unit price values are entered. If either quantity or unit price or both are left empty, then this field is available for entering a value. | |
| Sales Tax | Quick Create page and General tab of the Subcontract line details page | Editable field that is available for the user to enter a value. | |
| Total Amount | Quick Create page and General tab of the Subcontract line details page | This is a calculated field that is denotes the total amount of the subcontract line after including taxes. Calculated as Subtotal +Tax | |

*See Subcontracting in Project Operations - Early Access Scope

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
