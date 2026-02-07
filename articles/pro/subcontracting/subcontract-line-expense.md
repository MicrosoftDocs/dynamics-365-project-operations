---
title: Subcontract lines for expense categories
description: Learn how to record and manage subcontract expense lines in Dynamics 365. Follow our guide to streamline vendor purchases for your projects.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract lines for expense categories

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A subcontract in Dynamics 365 Project Operations can have a line for expense categories. Subcontract lines for expense categories allow a Project Manager to purchase categories of services or products from vendors that they can charge to a project.

To create a subcontract line for expense categories in Project Operations, complete the following steps.

1. In the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
1. On the **Subcontract Lines** tab, select **New** to create a new line.
1. On the **Quick Create** page, in the **Transaction Class** field, select **Expense**, and enter or select any other required field information.

The following table provides information about the fields on the **Subcontract line** details page and the **Quick Create** page.

| **Field** | **Description** | **Functional impact** |
| --- | --- | --- |
| Name | Name of the subcontract line to help with identification. | This name appears as the first column in all lookups based on subcontract lines. |
| Description | A brief description of the expense categories that you're purchasing on the subcontract line. | None |
| Line Type | This field has a default value of  **Quantity-based**. | None |
| Billing Method | This option set represents the two main contracting models supported by Project Operations: **Fixed Price** and **Time and Material**. | If you select the Fixed Price billing method, the system makes a milestone–based invoice schedule available for subcontract lines. |
| Transaction Class | This field has a default value of  **Time**. To create subcontract lines for purchasing products, set the  **Transaction Class**  field to  **Expense**.  | This value indicates that the subcontract line is used to record the purchase of a category of expenses to use on projects. |
| Transaction Category | Shows a list of active transaction categories in the system. |None |
| Requested Start | Enter the date when the categories of purchase must be available from the vendor. | Use the requested start date to pick a project price list from the project price lists attached to the subcontract. The cost of the category on the subcontract line comes from that price list. |
| Requested End | Enter the date when the categories of purchase are no longer needed. | This value triggers warnings when a project manager associates this subcontract line to specific expense estimates on the project that are required after this date. |
| Quantity Ordered | Quantity of the category being purchased from the vendor. | This value triggers warnings when a project manager overdraws from this quantity.|
| Unit Group | The default value is based on the default unit group that is set up for the selected category. |None |
| Unit | The default is based on the default unit set up for the selected category.  | The combination of **Category** and **Unit** is used as the default or computed for the unit price for the subcontract line.  |
| Unit Price | The default value uses the combination of the **Category** and **Unit** from the category prices related to the project price list, which is applicable for the requested start of the subcontract line. |None |
| Subtotal | This is a read-only field  that is calculated as Quantity X Unit price, if both the quantity and unit price values are entered. If either or both fields are blank, you can enter a value in this field. |None |
| Sales Tax | Enter the sales tax amount. |None |
| Total Amount | The total amount of the subcontract line including taxes. This field is calculated as Subtotal + Sales tax. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
