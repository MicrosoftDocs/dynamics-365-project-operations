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

Vendor invoices are created in Dynamics 365 Finance, in the Accounts Payable module . Creating Vendor invoices directly in Dataverse is not supported. 

### Creation from the Accounts Payable module in Finance
If your vendor invoice is meant for a subcontract in Dataverse, you will need to set the **Manual confirmation by PM is required** field Under **Project Management and accounting parameters **\> **Financial **\> **Vendor Invoice**. The value of this field determines if the vendor invoice should be auto confirmed in dataverse or if it needs manual confirmation. The value set here will default to the header of all project vendor invoices. If required, the value can be updated for each vendor invoice using the same field in the invoice header . 
If the value is set to **YES**, the vendor invoice is created in Finance and synchronized to dataverse with a **Draft** status. It means it needs to be validated by the PM and confirmed before it gets processed and posted to the specific project and ledger accounts in Finance. 
If the value of the field is set to **NO** , then the vendor invoice is auto confirmed and needs no further action. 

>[!NOTE]
> Vendor invoices created for subcontracts in dataverse can only be processed correctly if this field is set to **YES** . Time , material and expense cost actuals created by subcontractors can be matched with vendor invoice lines as a manual action by the project manager only if this flag is set to **Yes**.

1. Go to **Accounts Payable** \> **Invoices** \> **Pending Vendor Invoices** 
2. On the **Pending Vendor Invoices** page ,select **New** to create a new vendor invoice.

Alternatively, you can also create a Vendor Invoice, by going to **Accounts Payable** \> **Invoices** \> **Open Vendor Invoices \> New** 

On posting the Vendor invoice , the invoice becomes available in Dataverse for project manager's verification and processing. 

## Vendor Invoice Processing 

The Vendor invoice is created in dataverse with some fields from the vendor invoice recorded in D365 Finance and some defaulting from the subcontract.  

The following fields and related records will be copied from the subcontract to the header of the vendor invoice:
- Currency.
- Contracting unit.
- Payment terms.

On the Vendor invoice line, Project operations uses the following field values to default the subcontract and subcontract line reference:
- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task

>[!NOTE] 
>Fixed price subcontract lines are not supported in Project Operations



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
