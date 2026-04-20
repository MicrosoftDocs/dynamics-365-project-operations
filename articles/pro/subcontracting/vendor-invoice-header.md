---
title: Header details for vendor invoices
description: Learn about the vendor invoice header functionality in Microsoft Dynamics 365 Project Operations, including key fields and their impact on project costs.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Header details for vendor invoices

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article explains the functionality that the vendor invoice header provides in Microsoft Dynamics 365 Project Operations.

As project managers plan and execute projects, they might employ subcontractors and purchase products and services from vendors. During a project's execution, the project incurs costs from services, materials, and expense categories that the project manager procures through subcontracts with vendors. Vendors invoice these costs to projects by creating vendor invoices.

The following table provides information about the fields on vendor invoice headers in Project Operations.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice. | In all vendor invoice drop-down lists, the name of the vendor invoice appears in the first column to help you identify the vendor invoice. By default, when you create a vendor invoice from a subcontract, the **Name** field of the vendor invoice is set to a value that consists of the name of the subcontract plus the current date. |
| Description | A brief description of the services and products that are being invoiced on the vendor invoice. | None |
| Vendor | The name of the company that invoices for the products and services. This company should be an account record that has a relationship type of **Vendor** or **Supplier**. | <p>Based on the vendor that you select, the system automatically enters default values in the following fields:</p><ul><li>Currency</li><li>Price lists</li><li>Payment terms</li><li>Payment address</li></ul> |
| Subcontract | A reference to the subcontract for the vendor invoice. | <p>Based on the subcontract that you select, the system automatically enters default values in the following fields:</p><ul><li>Currency</li><li>Price lists</li><li>Payment terms</li><li>Payment address</li></ul><p>The subcontract that you select on the vendor invoice header appears by default on the vendor invoice lines and you can't change it there.</p> |
| Invoice date | The date for the cost actuals that the system creates when you confirm the vendor invoice. | The invoice date is also used to select the correct purchase price list either from the price lists that are attached to the related vendor or from project parameters. |
| Status reason | The status of the vendor invoice. | <p>The status determines where the vendor invoice is in the business process and whether it can be edited. Here are some of the available values:</p><ul><li>**Draft** – You can edit the vendor invoice.</li><li>**Confirmed** – The system verifies and confirms the vendor invoice. You can't edit or delete vendor invoices in this status.</li><li>**In process** – The vendor invoice is under review. You can edit vendor invoices in this status, but you can't delete them.</li><li>**Canceled** – The vendor invoice is canceled. You can't edit or delete vendor invoices in this status.</li></ul> |
| Currency | The currency that the vendor uses to invoice for the products and services on the vendor invoice. | On a vendor invoice that references a subcontract, the system enters the currency of the subcontract by default as the currency of the vendor invoice. On a vendor invoice that doesn't reference a subcontract, the system enters the default value from the vendor account record and you can change it. After you save a vendor invoice, you can no longer edit the currency. |
| Contracting unit | The division of the company that is responsible for receiving the services and products from the vendor. | None |
| Payment terms | The terms of payment on vendor invoices that you issue. The system automatically enters the default value from the vendor account record. | The system copies payment terms from a subcontract to all vendor invoices that relate to the subcontract. You can update payment terms if the vendor invoice has a status of **Draft**. |
| Payment address | The address of the vendor that you must send payments to. The system automatically enters the default value from the vendor account record. | The system copies the payment address from a subcontract as the payment address to all vendor invoices that you create for that subcontract. You can update the payment address if the vendor invoice has a status of **Draft**. |
| Subtotal | If the vendor invoice has no lines, enter the invoice subtotal before taxes. If the vendor invoice has lines, this field is read only. In this case, the amount that is shown is the subtotal amount from all the lines on the vendor invoice. | None |
| Total tax | If the vendor invoice has no lines, enter the total taxes on the subcontract. If the vendor invoice has lines, this field is read only. In this case, the amount that is shown is the sum of tax amounts from all the lines on the vendor invoice. | None |
| Total amount | This calculated field shows the total amount of the vendor invoice after taxes are included. | None |

> [!NOTE]
> You can't change the following fields on a vendor invoice after you save the vendor invoice: **Vendor**, **Subcontract**, **Currency**, **Contracting unit**, and **Payment terms**. If you need to change these fields on a vendor invoice, delete the vendor invoice and create a new vendor invoice.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
