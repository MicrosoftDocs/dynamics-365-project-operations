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

1. In the navigation pane, select **Subcontracts**, and on the **Subcontract** page, select **New**.
2. Enter the required information, and then select **Save**.

    The following table provides information about the fields on the Subcontract header page.

    | **Field** | **Description** |**Functional Impact** |
    | --- | --- |  --- | 
    | Name | The name of the subcontract. |In all dropdowns that list subcontracts, the name of the subcontract will be shown as the first column and will help the user in identifying the subcontract| 
    | Description | A brief description of services and products that are being purchased on the subcontract. |None|
    | Vendor | The name of the company that the products and services are being purchased from. This account record has a relationship type of **Vendor** or **Supplier**. |Currency, Price Lists, Payment Terms, Payment Address, Bill To Address, Bill To Name and Vendor Account Manager are defaulted based on the vendor selected.|
    | Subcontract Date | The date the subcontract is created. | Date of the subcontract will be used to default the correct Purchase Price Lists from the list of price lists attached to the related Vendor or from Project Parameters.|
    | Status Reason | The status of the subcontract. | Status of the Subcontract will determine if the Subcontract can be edited. Only Subcontracts in Draft status can be edited by the user| 
    | Currency | The currency in which products and services are purchased. The value in this field defaults from the vendor account but can be changed.|Currency of the subcontract will be used to default Purchase Price Lists from the list of price lists attached to the related Vendor or from Project Parameters. Price lists in any other currency can't be associated to the subcontract. The cost of time, expenses and materials delievered by vendor resources from this subcontract will be recorded on the project, in this currency. Once saved, currency on the subcontract cannot be changed.|
    | Contracting Unit | The division of the company that is entering into a purchase contract or a subcontract with the vendor. |None|
    | Payment terms | The terms of payment on the vendor invoices that are issued on this subcontract. The value in this field defaults from the vendor account record. |Payment terms from the subcontract will copied on all vendor invoices that are related to this subcontract. Payment terms can be updated based on the editability state of the Subcontract.| 
    | Payment Address | The address of the vendor where payments must be sent to. The value in this field defaults from the vendor account record. |Payment address from the subcontract will copied as Payment address on all vendor invoices created for this subcontract. Payment address can be updated based on the editability state of the Subcontract.|
    | Bill To Name | The name of the person or division in the vendor's company that will send the invoice. The value in this field defaults from the vendor account record |Bill To Name  from the subcontract will be copied on all vendor invoices that are related to this subcontract. Bill To Name can be updated based on the editability state of the Subcontract.|
    | Bill to Address | The address used on invoices from this vendor. The value in this field defaults from the vendor account record. | This address is also used as the 'invoice from' address on vendor invoices created for this subcontract.
    | Subtotal | If a subcontract has no lines, user will be able to enter a value in this field that denotes the order subtotal before taxes. If the subcontract has lines, this field is read only. The amount displayed is the subtotal amount from all the lines on the subcontract. |None|
    | Total Tax | If a subcontract has no lines, user can enter a value in this field that denotes the taxes on this subcontract. If the subcontract has lines, this field is read only. The amount displayed is the sum of the tax amount from all the lines on the subcontract. |None|
    | Total Amount |  This calculated field shows the total amount of the subcontract after taxes are included.  |None|
    | Date Confirmed | The date that the subcontract was confirmed.  | None|
    | Requested By | The value in this field defaults to the name of the user who creates the subcontract. This value can be changed by the creator of the subcontract to indicate that person on behalf of whom they are creating the subcontract.  |None|
    | Vendor Account Manager | The name of the primary contact of the vendor account. The value in this field defaults from the vendor account record. This field value can be changed by the user to select a different contact as the vendor account manager of the subcontract. |Email alerts and price negotiations can be configured and sent by this contact. |


