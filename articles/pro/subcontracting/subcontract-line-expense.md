---
title:  Subcontract lines for expense categories
description: This topic explains how to record subcontract lines for expense and use the fields to record the purchase of time from vendors.
author: rumant
ms.date: 08/06/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

#  Subcontract lines for expense categories

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract in Dynamics 365 Project Operations can have a line for expense categories. Subcontract lines for expense categories allow a Project Manager to purchase categories of services or products from vendors that they can charge to a project.

To create a subcontract line for expense categories in Project Operations, complete the following steps.

1. In the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
2. On the **Subcontract Lines** tab, select **New** to create a new line.
3. On the **Quick Create** page, in the **Transaction Class** field, select **Expense** and enter or select any other required field information.

The following table provides information about the fields on the **Subcontract line** details page and the **Quick Create** page.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the subcontract line to help with identification | This will be shown as the first column in all look ups based on Subcontract lines |
| Description | A brief description of the expense categories that are being purchased on the subcontract line. | None |
|Line Type | This field has a default value of  **Quantity-based**. |None |
| Billing Method | This is an option set that represents the two main contracting models supported by Project Operations:</br> -  **Fixed Price**</br> -  **Time and Material** | A milestone – based invoice schedule is made available for Subcontract lines where Billing method selected is Fixed Price. |
| Transaction Class | This field has a default value of  **Time**. To create subcontract lines for purchasing products, set the  **Transaction Class**  field to  **Expense**.  | This indicates that the subcontract line is being used to record the purchase of a category of expenses to be used on projects |
| Transaction Category | Shows a dropdown list of active transaction categories in the system. |None |
| Requested Start | Date when the categories of purchase must be available from the vendor | Requested start is used to pick a project price list from the project price lists attached to the subcontract. Cost of the category on the subcontract line is defaulted from that price list. |
| Requested end | Date when the categories of purchase would no longer be needed | This will be used to show warnings when a project manager is associating this subcontract line to specific expense estimates on the project that are required after this date. |
| Quantity Ordered | Quantity of the category being purchased from the vendor | When a project manager over-draws from this quantity, a warning will be shown. |
| Unit Group | This field value defaults based on the default unit group that is set up for the selected category. |None |
| Unit | This field value defaults based on the default unit set up for the selected category.  | The combination of Category and Unit will be used to default the unit price on the Subcontract line. |
| Unit Price | The unit price field value defaults from the combination of the category and unit from the category prices related to the project price list which is applicable for the requested start of the subcontract line. |None |
| Subtotal | This read-only field is automatically calculated as the quantity X unit price if both the quantity and unit price values are entered. If either or both fields are empty, you can manually enter a value in this field. |None |
| Sales Tax | Enter the sales tax amount. |None |
| Total Amount | The total amount of the subcontract line including taxes. This field is calculated as subtotal + sales tax. |None |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
