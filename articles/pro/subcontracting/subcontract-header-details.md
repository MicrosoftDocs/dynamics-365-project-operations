---
title: Header details for subcontracts
description: This article explains the functionality provided on the subcontract header in Project Operations.
author: rumant
ms.date: 09/14/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Header details for subcontracts

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article explains the functionality provided on the subcontract header in Dynamics 365 Project Operations.

As a Project Manager plans and executes projects, they may employ subcontractors and purchase products and services from vendors. When a Project Manager needs to purchase products or services, they can create a subcontract in Project Operations.

To create a subcontract, complete the following steps.

1. In the navigation pane, select **Subcontracts**, and on the **Subcontract** page, select **New**.
2. Enter the required information, and then select **Save**.

    The following table provides information about the fields on the **Subcontract header** page.

    | Field | Description |Functional Impact |
    |---|------|---| 
    | Name | The name of the subcontract. | In all subcontract drop-down lists, the name of the subcontract is listed in the first column to help you identify the subcontract. | 
    | Description | A brief description of services and products that are being purchased on the subcontract. | None |
    | Vendor | The name of the company that the products and services are being purchased from. This account record has a relationship type of **Vendor** or **Supplier**. | Based on the vendor that is selected, default values are automatically entered for the following fields:<br/> **• Currency** </br> **• Price Lists** </br> **• Payment Terms**</br> **• Payment Address**</br> **• Bill To Address**</br> **• Bill To Name** </br>**• Vendor Account Manager**|
    | Subcontract Date | The date when the subcontract is created. | The subcontract date is used to select the correct purchase price list either from the price lists that are attached to the related vendor or from the project parameters. |
    | Status Reason | The status of the subcontract. | The status determines where the subcontract is in the business process and whether it can be edited. <br/>Values include:<br>• **Draft**: The subcontract can be edited. You can only edit subcontracts with a status of **Draft**.<br/>• **Confirmed**: The negotiation with the vendor is complete and the subcontract is approved for delivery. <br/>• **Closed**: The delivery on the subcontract is complete.<br/>• **Canceled**: The subcontract was canceled and no delivery is planned.  | 
    | Currency | The currency that products and services are purchased in. The default value is automatically entered from the vendor account, but it can be changed. | The currency of the subcontract is used to select the purchase price list either from the price lists that are attached to the related vendor or from the project parameters. Price lists in another currency can't be associated with the subcontract. The cost of time, expenses, and materials that vendor resources deliver from this subcontract are recorded in this currency on the project. After the subcontract record is saved, the currency on the subcontract can't be changed.|
    | Contracting Unit | The division of the company that is entering into a purchase contract or a subcontract with the vendor. | None |
    | Payment terms | The terms of payment on vendor invoices that are issued on this subcontract. The default value is automatically entered from the vendor account record. | Payment terms from the subcontract are copied to all vendor invoices that are related to this subcontract. Payment terms can be updated if the subcontract has a status of **Draft**. | 
    | Payment Address | The address of the vendor that payments must be sent to. The default value is automatically entered from the vendor account record. | The payment address from the subcontract is copied as the payment address to all vendor invoices that are created for this subcontract. The payment address can be updated if the subcontract has a status of **Draft**.|
    | Bill To Name | The name of the person or division in the vendor's company that will send the invoice. The default value is automatically entered from the vendor account record. | The **Bill To Name** value from the subcontract is copied to all vendor invoices that are related to this subcontract. This field can be updated if the subcontract has a status of **Draft**.|
    | Bill To Address | The address that is used on invoices from the vendor. The default value is automatically entered from the vendor account record. | This address is the "invoice from" address on vendor invoices that are created for this subcontract. |
    | Subtotal | If a subcontract has no lines, enter the order subtotal before taxes. If the subcontract has lines, this field is read only. The amount that is shown is the subtotal amount from all the lines on the subcontract. | None |
    | Total Tax | If a subcontract has no lines, enter the total taxes on this subcontract. If the subcontract has lines, this field is read only. The amount that is shown is the sum of the tax amount from all the lines on the subcontract. | None |
    | Total Amount | This calculated field shows the total amount of the subcontract after taxes are included. | None |
    | Date Confirmed | The date when the subcontract was confirmed. | None |
    | Requested By | By default, this field is set to the name of the user who creates the subcontract. However, the creator of the subcontract can change the value to indicate the person that they are creating the subcontract on behalf of. | None |
    | Vendor Account Manager | The name of the primary contact of the vendor account. The default value is automatically entered from the vendor account record. You can select a different contact as the vendor account manager of the subcontract. | You can set up email alerts to notify the contact when changes are made to the subcontract as a result of price negotiations. |
