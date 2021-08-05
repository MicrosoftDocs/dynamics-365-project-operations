---
title: Header details for subcontracts
description: This topic explains the functionality provided on the subcontract header in Project Operations.
author: rumant
ms.date: 08/05/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Header details for subcontracts

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This topic explains the functionality provided on the subcontract header in Dynamics 365 Project Operations.

As a Project Manager plans and executes projects, they may employ subcontractors and purchase products and services from vendors. When a Project Manager needs to purchase products or services, they can create a subcontract in Project Operations.

To create a subcontract, complete the following steps.

1. In the navigation pane, select **Subcontracts**, and on the **Subcontact** page, select **New**.
2. Enter the required information, and then select **Save**.

    The following table provides information about the fields on the Subcontract header page.

    | **Field** | **Description** |
    | --- | --- | 
    | Name | The name of the subcontract. |
    | Description | A brief description of services and products that are being purchased on the subcontract. |
    | Vendor | The name of the company that the products and services are being purchased from. This account record has a relationship type of **Vendor** or **Supplier**. |
    | Subcontract Date | The date the subcontract is created. |
    | Status Reason | The status of the subcontract. |
    | Currency | The currency in which products and services are purchased. The value in the currency field defaults from the vendor account but can be changed. Project price lists that are used for pricing products and services on the subcontract should be in this currency. Price lists in any other currency can't be associated to the subcontract. The cost of products and services incurred on this subcontract will be recorded on the project in this currency. |
    | Contracting Unit | The division of the company that is entering into a purchase contract or a subcontract with the vendor. |
    | Payment terms | The terms of payment on the vendor invoices that are issued on this subcontract. The value in this field defaults from the vendor account record. |
    | Payment Address | The address where the payment on vendor invoices is sent. The value in this field defaults from the vendor account record. |
    | Bill To Name | The name of the person or division in the vendor's company that will send the invoice. The value in this field defaults from the vendor account record and will be used as the name of the primary contact on vendor invoices created for this subcontract. |
    | Bill to Address | The address used on invoices from this vendor. The value in this field defaults from the vendor account record. This address is also used as the invoice from address on vendor invoices created for this subcontract. |
    | Subtotal | If a subcontract has no lines, enter a value in this field that denotes the order subtotal before taxes. If the subcontract has lines, this field is read-only. The amount displayed is the subtotal amount from all the lines on the subcontract. |
    | Total Tax | If a subcontract has no lines, enter a value in this field that denotes the taxes on this subcontract. If the subcontract has lines, this field is read-only. The amount displayed is the sum of the tax amount from all the lines on the subcontract. |
    | Total Amount |  This calculated field shows the total amount of the subcontract after taxes are included.  |
    | Date Confirmed | The date that the subcontract was confirmed.  |
    | Requested By | The value in this field defaults to the name of the user who creates the subcontract. This value can be changed by the creator of the subcontract to indicate that person on behalf of whom they are creating the subcontract.  |
    | Vendor Account Manager | The name of the primary contact of the vendor account. The value in this field defaults from the vendor account record. This field value can be changed by the user to select a different contact as the vendor account manager of the subcontract. Email alerts and price negotiations can be configured and sent by this contact. |


