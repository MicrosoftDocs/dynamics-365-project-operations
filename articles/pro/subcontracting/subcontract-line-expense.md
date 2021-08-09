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

| **Field** |  **Description** |
| ----------| ---------------- |
| Name | The name of the subcontract line. |
| Description | A brief description of the service or product categories that are being purchased on the subcontract line. |
| Line Type | This field has a default value of **Quantity-based**.  |
| Billing Method | The billing method of the subcontract line. Based on the billing method of the line, a milestone-based invoice schedule is available for the fixed-price billing method.  |
| Transaction Class | This field has a default value of **Time**. To create subcontract lines for purchasing products, set the **Transaction Class** field to **Expense**. This field value indicates that the subcontract line is being used to record a purchase of a category of products or services to be used on projects. |
| Transaction Category | Select the transaction category. |
| Requested Start | The date when the purchase categories must be available from the vendor. The requested start is used to pick a project price list from the project price lists attached to the subcontract. The cost of the category on the subcontract line defaults from that price list. |
| Requested end | The date when the purchase categories are no longer needed. This date calls a warning when a project manager associates this subcontract line with specific expense estimates on the projects that are dated after this date. |
| Quantity Ordered | The quantity of the category being purchased from the vendor. When a project manager overdraws from the purchased quantity, a warning will occur.  |
| Unit Group | This field value defaults based on the default unit group that is set up for the selected category. |
| Unit | This field value defaults based on the default unit set up for the selected category. The combination of category and unit is used to default the unit price on the subcontract line. |
| Unit Price | The unit price field value defaults from the combination of the category and unit from the category prices related to the project price list which is applicable for the requested start of the subcontract line.  |
| Subtotal | This read-only field is automatically calculated as the quantity unit price if both the quantity and unit price values are entered. If either or both of the fields are empty, you can manually enter a value in this field.  |
| Sales Tax | Enter the sales tax amount.  |
| Total Amount | The total amount of the subcontract line including taxes. This field is calculated as subtotal + sales tax.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
