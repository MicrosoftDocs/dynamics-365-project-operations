---
title: Header details for vendor invoices
description: This article explains the functionality that is provided on the vendor invoice header in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 12/15/2023
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Header details for vendor invoices

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article explains the functionality that is provided on the vendor invoice header in Microsoft Dynamics 365 Project Operations.

As project managers plan and execute projects, they might employ subcontractors and purchase products and services from vendors. During a project's execution, costs are incurred from services, materials, and expense categories that are procured on subcontracts with vendors. Vendors invoice these costs to projects by creating vendor invoices.

The following table provides information about the fields on vendor invoice headers in Project Operations.

| Field | Description | Functional impact |
| --- | --- | --- |
| Name | The name of the vendor invoice. | In all vendor invoice drop-down lists, the name of the vendor invoice is listed in the first column to help you identify the vendor invoice. By default, when a vendor invoice is created from a subcontract, the **Name** field of the vendor invoice is set to a value that consists of the name of the subcontract plus the current date. |
| Description | A brief description of the services and products that are being invoiced on the vendor invoice. | None |
| Vendor | The name of the company that is invoicing for the products and services. This company should be an account record that has a relationship type of **Vendor** or **Supplier**. | <p>Based on the vendor that is selected, default values are automatically entered in the following fields:</p><ul><li>Currency</li><li>Price lists</li><li>Payment terms</li><li>Payment address</li></ul> |
| Subcontract | A reference to the subcontract for the vendor invoice. | <p>Based on the subcontract that is selected, default values are automatically entered in the following fields:</p><ul><li>Currency</li><li>Price lists</li><li>Payment terms</li><li>Payment address</li></ul><p>The subcontract that is selected on the vendor invoice header is entered by default on the vendor invoice lines and can't be changed there.</p> |
| Invoice date | The date for the cost actuals that will be created when the vendor invoice is confirmed. | The invoice date is also used to select the correct purchase price list either from the price lists that are attached to the related vendor or from project parameters. |
| Status reason | The status of the vendor invoice. | <p>The status determines where the vendor invoice is in the business process and whether it can be edited. Here are some of the available values:</p><ul><li>**Draft** – The vendor invoice can be edited.</li><li>**Confirmed** – The vendor invoice was verified and confirmed. Vendor invoices in this status can't be edited or deleted.</li><li>**In process** – The vendor invoice is being reviewed. Vendor invoices in this status can be edited, but they can't be deleted.</li><li>**Canceled** – The vendor invoice was canceled. Vendor invoices in this status can't be edited or deleted.</li></ul> |
| Currency | The currency that the vendor is invoicing in for the products and services on the vendor invoice. | On a vendor invoice that references a subcontract, the currency of the subcontract is entered by default as the currency of the vendor invoice. On a vendor invoice that doesn't reference a subcontract, the default value is entered from the vendor account record and can be changed. After a vendor invoice is saved, the currency can no longer be edited. |
| Contracting unit | The division of the company that is responsible for receiving the services and/or products from the vendor. | None |
| Payment terms | The terms of payment on vendor invoices that are issued. The default value is automatically entered from the vendor account record. | Payment terms from a subcontract are copied to all vendor invoices that are related to the subcontract. Payment terms can be updated if the vendor invoice has a status of **Draft**. |
| Payment address | The address of the vendor that payments must be sent to. The default value is automatically entered from the vendor account record. | The payment address from a subcontract is copied as the payment address to all vendor invoices that are created for that subcontract. The payment address can be updated if the vendor invoice has a status of **Draft**. |
| Subtotal | If the vendor invoice has no lines, enter the invoice subtotal before taxes. If the vendor invoice has lines, this field is read only. In this case, the amount that is shown is the subtotal amount from all the lines on the vendor invoice. | None |
| Total tax | If the vendor invoice has no lines, enter the total taxes on the subcontract. If the vendor invoice has lines, this field is read only. In this case, the amount that is shown is the sum of tax amounts from all the lines on the vendor invoice. | None |
| Total amount | This calculated field shows the total amount of the vendor invoice after taxes are included. | None |

> [!NOTE]
> The following fields on a vendor invoice can't be changed after the vendor invoice is saved: **Vendor**, **Subcontract**, **Currency**, **Contracting unit**, and **Payment terms**. If any changes are required to these fields on a vendor invoice, you must delete the vendor invoice and create a new vendor invoice.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
