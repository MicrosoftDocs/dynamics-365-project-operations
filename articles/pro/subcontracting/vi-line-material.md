---
title: Vendor invoice lines for products
description: Learn how to record vendor invoice lines for products in Microsoft Dynamics 365 Project Operations. Understand fields, processes, and best practices for accurate tracking.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoice lines for products

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

A vendor invoice in Microsoft Dynamics 365 Project Operations can have vendor invoice lines for products (also referred to as materials). Project managers can use vendor invoice lines for products to record the costs of products that they purchase on projects.

Vendor invoice lines for products might or might not reference a subcontract line for materials. If a vendor invoice line for products references a subcontract, project managers can match and verify the products that the vendor invoice line invoices against the use of purchased products that project managers record and approve.

The following table provides information about the fields on vendor invoice lines for products.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice line, to help with identification. | This name appears as the first column in all lookups that are based on vendor invoice lines. |
| Description | A brief description of the products that the vendor is invoicing on the vendor invoice line. | None |
| Subcontract | The subcontract that the products were originally ordered on. | When you select a subcontract for the vendor invoice, all lines on the vendor invoice inherit that selection. A vendor invoice can't have vendor invoice lines that reference different subcontracts. |
| Subcontract line | The subcontract line that the products were ordered on. The list of subcontract lines that you can select is limited to the lines on the selected subcontract. | When you select a subcontract line on a vendor invoice line for products, default values for the **Project**, **Task**, and **Product** fields come from the corresponding fields on the subcontract line. If the selected subcontract line has values in the **Project**, **Task**, and **Product** fields, the values of the corresponding fields on the vendor invoice line can't differ from those values. |
| Transaction date | The date when the cost actual of the vendor invoice line is recorded on the project. | None|
| Transaction class | When products are invoiced, set this field to **Material**. | The value **Material** indicates that the vendor invoice line is used to record the invoice amount for materials that the vendor purchased. |
| Project | The name of the project that the products that the vendor is invoicing were used on. | This field is required and can't be left blank. |
| Task | The name of the project task that the products that the vendor is invoicing were used on. This field is available only if a project is selected. Selection of a project task is optional. | If you leave this field blank, the project manager can match the vendor invoice line to the purchased product that is used on any task of the project. If the vendor invoice line doesn't reference a subcontract line, and this field is left blank, the cost actual that the vendor invoice line creates isn't linked to any unbilled sales actuals. In this case, if task-based billing is set up, the costs can't be invoiced to the end customer. |
| Select product | Select whether the product that the vendor is invoicing is an existing product from the catalog or a write-in product. | The default value comes from the subcontract line when you select a subcontract line. |
| Product | Select the product from the catalog. If the product is a write-in product, enter the name of the product. | This field is used to enter default purchase prices for existing products. |
| Quantity | Enter the quantity of material that the vendor is invoicing on this invoice line. | None |
| Unit group | Select the unit group of the unit that the quantity that the vendor is invoicing is expressed in. | None |
| Unit | The default value is the base unit of the unit group that is selected. You can change this value to pay in any unit of the selected unit group. | The combination of **Product** and **Unit** values is used as the default or computed value for the **Unit price** field on the vendor invoice line. |
| Unit price | The default unit price uses the combination of **Product** and **Unit** values from the project price list that's applicable to the transaction date of the vendor invoice line. | None |
| Subtotal | This read-only field is calculated as *Quantity* &times; *Unit price*, if you enter values in both the **Quantity** field and the **Unit price** field. If one or both those fields are blank, you can enter a value in this field. | None |
| Sales tax | Enter the sales tax amount. | None |
| Total amount | The total amount of the vendor invoice line, including taxes. This field is calculated as *Subtotal* + *Sales tax*. | None |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
