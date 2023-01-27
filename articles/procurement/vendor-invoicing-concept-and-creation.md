---
title: Vendor invoicing concept and creation
description: This article explains how to enable non-stocked materials and pending vendor invoices.
author: suvaidya
ms.date: 08/23/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: suvaidya
---

## # Vendor invoicing - Concept and creation

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Vendor invoicing in Microsoft Dynamics 365 Project Operations can be used to record costs from deliveries of services and/or materials on a project by vendors.

When services and/or materials are subcontracted to a vendor, a subcontract represents the contractual agreement with that vendor. As the vendor delivers the services, or the materials are received and used on project tasks, costs are recorded on the project. Periodically, the vendor sends invoices that are verified and matched with costs that are recorded on the project. After the verification process is completed, the vendor invoice is confirmed and released for payment.

## Scenarios for use

Vendor invoices in Project Operations can be used to support two distinct scenarios.

### Customers use the full subcontracting experiences

Vendor invoice experiences provide a way to verify and match time entries, material usage, and expense entries that reference subcontracted components with vendor invoice lines. This process can be used to verify the accuracy of the vendor invoice lines. After the verification process is completed and the vendor invoice is confirmed, the application will reverse the actuals that were recorded by approved time, expense, and material usage logs, and create new cost actuals by using the vendor invoice lines.

### Customers don't use the full subcontracting experiences but want to have a unified view of costs on projects in Project Operations

If you're tracking the subcontract process in a third-party system, you can record costs from that third-party system to Project Operations by creating vendor invoices that don't reference subcontracts. In this way, your project managers can have single, unified view of all costs on a given project.

## Creation of vendor invoices in Project Operations

In the resource/non -stocked deployment, Vendor invoices are created in F&O from the Accounts Payable module in Finance. Creating Vendor invoices in Dataverse is not supported in this deployment mode. 

### Creation from the Accounts Payable module in Finance

1. Go to **Accounts Payable** \> **Invoices** \> **Pending Vendor Invoices** 
2. On the **Pending Vendor Invoices** page ,select **New** to create a new vendor invoice.

Alternatively, you can also create a Vendor Invoice, by going to **Accounts Payable** \> **Invoices** \> **Open Vendor Invoices \> New** 

On posting the Vendor invoice , the invoice becomes available in Dataverse for verification and processing. 

## Vendor Invoice processing 

In resource/non stocked scenario, vendor invoices containing a reference to a subcontract will require PM confirmation. 
Under **Project Management and accounting parameters **\> **Financial **\> **Vendor Invoice** \> , set the value for **Manual confirmation by PM is required** field. The value of this field when set to "No" implies that the vendor invoice should be auto confirmed. When set to "Yes" , it implies that the vendor invoice needs manual confirmation by the PM in dataverse.  
The value set here will default to the header of all vendor invoices created in the resource/non stocked scenario. If required, the value can be updated for each vendor invoice using the same field in the invoice header . 
If the value is set to "YES", the vendor invoice is created in dataverse with a "draft" status ,and when set to "No" it is created with a "confirmed" status. 

The following fields and related records will be copied from the subcontract to the header of the vendor invoice:
- Currency.
- Contracting unit.
- Payment terms.

For Time and material subcontract lines, the following fields and related records will be used to match the subcontract lines to the vendor invoice line:
- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task
The subcontract and subcontract line references will default on the VI line, when the Project, Transaction class, Product ID, transaction category , task and Role on the subcontract match that of the Vendor Invoice line submitted in F&O. 

Fixed price subcontract lines are not supported in this deployment mode. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
