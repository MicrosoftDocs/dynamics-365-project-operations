---
title: Header details for Vendor Invoice
description: This topic explains the functionality provided on the Vendor Invoice header in Dynamics 365 Project Operations.
ms.date: 03/15/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Header details for Vendor Invoice

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This topic explains the functionality provided on the vendor invoice header in Dynamics 365 Project Operations.

As a Project Manager plans and executes projects, they may employ subcontractors and purchase products and services from vendors. During a project&#39;s execution, costs are incurred from services, materials and expense categories procured on subcontracts with vendors. These costs are invoiced by vendors to projects by creating vendor invoices

The following table provides information about the fields on the  **Vendor Invoice header**  in Project Operations.

| **Field** | **Description** | **Functional Impact** |
| --- | --- | --- |
| Name | The name of the vendor invoice. | In all vendor invoice drop-down lists, the name of the vendor invoice is listed in the first column to help you identify the vendor invoice.When a vendor invoice is created from a subcontract, the name field of the vendor invoice is defaulted using the name of the subcontract with the current date appended. |
| Description | A brief description of services and products that are being invoiced on this vendor invoice. | None |
| Vendor | The name of the company that is invoicing for the products and services This should be an Account record has a relationship type of  **Vendor**  or  **Supplier**. | Based on the vendor that is selected, default values are automatically entered for the following fields:<br>**• Currency**<br>**• Price Lists**<br>**• Payment Terms**<br>**• Payment Address** |
| Subcontract | Reference to the subcontract for this vendor invoice | Based on the subcontract that is selected, default values are automatically entered for the following fields:<br>**• Currency**<br>**• Price Lists**<br>**• Payment Terms**<br>**• Payment Address**| Subcontract selected on the vendor invoice header also defaults on the vendor invoice lines and cannot be changed to a different subcontract on the vendor invoice line |
| Invoice Date | The date for the cost actuals that will get created when the Vendor Invoice is confirmed | The invoice date is also used to select the correct purchase price list either from the price lists that are attached to the related vendor or from project parameters. |
| Status Reason | The status of the vendor invoice. | The status determines where the vendor invoice is in the business process and whether it can be edited. Values include: <br>•  **Draft** : The vendor invoice can be edited. <br>•  **Confirmed** : Vendor invoice is verified and confirmed. Vendor invoices in this status cannot be edited or deleted. <br>•  **In process** : Vendor invoice is being reviewed. Vendor invoices in this status can be edited but cannot be deleted. <br>•  **Canceled** : Vendor Invoice was canceled. Vendor invoices in this status cannot be edited or deleted. |
| Currency | Currency in which the vendor is invoicing for the products and services on this vendor invoice | On a vendor invoice that references a subcontract, the currency of the vendor invoice gets defaulted from the currency of the subcontract. On a vendor invoice that does not reference a subcontract, currency is defaulted from the Vendor Account record and can be changed. Once a vendor invoice is saved, currency can no longer be edited |
| Contracting Unit | The division of the company that is responsible for receiving the services and/or products from the vendor. | None |
| Payment terms | The terms of payment on vendor invoices that are issued. The default value is automatically entered from the vendor account record. | Payment terms from the subcontract are copied to all vendor invoices that are related to this subcontract. Payment terms can be updated if the vendor invoice has a status of  **Draft**. |
| Payment Address | The address of the vendor that payments must be sent to. The default value is automatically entered from the vendor account record. | The payment address from the subcontract is copied as the payment address to all vendor invoices that are created for this subcontract. The payment address can be updated if the vendor invoice has a status of  **Draft**. |
| Subtotal | If a vendor invoice has no lines, enter the invoice subtotal before taxes. If the vendor invoice has lines, this field is read only. The amount that is shown is the subtotal amount from all the lines on the vendor invoice. | None |
| Total Tax | If a vendor invoice has no lines, enter the total taxes on this subcontract. If the vendor invoice has lines, this field is read only. The amount that is shown is the sum of the tax amount from all the lines on the vendor invoice. | None |
| Total Amount | This calculated field shows the total amount of the vendor invoice after taxes are included. | None |

>[!Note] 
>The following fields on a vendor invoice cannot be changed once the vendor invoice is saved. Vendor, Subcontract, Currency, Contracting Unit and Payment terms. If any changes are required to these fields on a vendor invoice, you will have to delete the vendor invoice and create a new vendor invoice.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
