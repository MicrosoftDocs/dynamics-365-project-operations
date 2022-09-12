---
title: Vendor invoicing concept and creation
description: This article explains how to enable non-stocked materials and pending vendor invoices.
author: suvaidya
ms.date: 9/12/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Vendor invoicing - Concept and creation

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use this feature, **Enable subcontract actuals processing with Project Operations for resource based scenarios** using the **feature management** workspace.

Vendor invoicing in Microsoft Dynamics 365 Project Operations can be used to record costs from deliveries of services and/or materials on a project complete by vendors.

When services and/or materials are subcontracted to a vendor, a subcontract represents the contractual agreement with that vendor. As the vendor delivers the services, or the materials are received and used on project tasks, costs are recorded on the project. Periodically, the vendor sends invoices that are verified and matched with costs that are recorded on the project. After the verification process is completed, the vendor invoice is confirmed and released for payment.

## Scenarios for use

Vendor invoices in Project Operations can be used to support two distinct scenarios.
 - Customers use the full subcontracting experiences.
 - Customers don't use the full subcontracting experiences but want to have a unified view of costs on projects in Project Operations.

### Customers use the full subcontracting experiences

Vendor invoice experiences provide a way to verify and match time entries, material usage, and expense entries that reference subcontracted components with vendor invoice lines. This process can be used to verify the accuracy of the vendor invoice lines. After the verification process is completed and the vendor invoice is confirmed, the system will reverse the actuals that were recorded by approved time, expense, and material usage logs, and then create new cost actuals using the vendor invoice lines.

### Customers don't use the full subcontracting experiences but want to have a unified view of costs on projects in Project Operations

If you're tracking the subcontract process in a third-party system, you can record costs from that third-party system to Project Operations by creating vendor invoices that don't reference subcontracts. In this way, your project managers can have single, unified view of all costs on a given project.

## Creation of vendor invoices in Project Operations

Vendor invoices are created in Microsoft Dynamics 365 Finance, using the **Accounts Payable** module. Creating vendor invoices directly in Microsoft Dataverse is not supported. 

### Set up vendor invoice verification 
If the vendor invoice is meant for a subcontract in Dataverse, you will need to enable the **Manual confirmation by PM is required** parameter.

The value of this field determines if the vendor invoice should be **auto confirmed** in Dataverse, or if it needs manual confirmation. The value set here will default to the header of all project vendor invoices. If required, the value can be updated for each vendor invoice using the same field in the invoice header. 

If the value is set to **YES**, the vendor invoice is created in Finance and synchronized to Dataverse with a **Draft** status. The invoice needs to be **Validated & verified by the Project manager** and confirmed before it gets processed and posted to the specific **project** and **ledger accounts** in **Finance**. 

If the value of the field is set to **NO**, then the vendor invoice is auto confirmed and needs no further action. 

To set up vendor invoice verification, follow these steps.

1.	In **Finance**, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1.	On the **Financial** tab, Select **Manual verification by PM is required** if as per company policy, vendor invoice verification is needed for subcontractor vendor invoices. It will be defaulted to the **pending vendor invoice form**. In case **verification by Project manager** is not required in Dataverse then don’t select this field. 

>[!NOTE]
> Vendor invoices created for subcontracts in Dataverse can only be processed correctly if this field is set to **YES**. Time, material, and expense cost actuals created by subcontractors can be matched with vendor invoice lines as a manual action by the project manager only if this flag is set to **Yes**.

### Set up a procurement integration account for vendor invoices

When a vendor invoice is posted in Finance for Project Operations – Integrated environment (non-stock), then financials are posted into the **Procurement integration account**. The system generates the actuals in Dataverse for the posted invoice. These actuals are posted in Finance using the **Project integration journal**. **Posting of integration journal** posts the actual cost and reverses the **Procurement integration account**.

To set up a procurement integration account for vendor invoices, follow these steps.

1.	In **Finance**, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1.	Select **Project operations on Dynamics 365 customer engagement tab**.
1.	Select **Materials** > **Procurement integration account**.

### Create and post subcontract vendor invoices

When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in Finance. 

1.	In Finance, go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.
1.	On the **Action Pane**, select **New** to create a new vendor invoice.
1.	Select the **Invoice account** as a **Subcontractor** on the invoice header.
1.	Select the **Invoice date**.
1.	Select the **Header** tab, and then select **Manual verification by PM is required**. This field is defaulted from the **Project management and accounting parameters**. However, it can be changed at vendor invoice level.  
1.	On the **Pending vendor invoice** page, **Invoice line** fast tab, select **Add line** to create a vendor invoice line.
1.	Select the **Procurement category** created for subcontract lines, enter the **unit price**, **Unit of measurement**, and **Quantity**.
1.	In the vendor invoice lines area, select the **Project** tab.
1.	Select the *Project** against which the subcontract invoice is shared by the subcontractor.
1.	Select the **Project category**. It can be of any type of **Item**, **Expense**, or **Items**.
1.	Select the **Role** only if the selected **project category** is of **Hour** type. 
1.	Select **Post** to post the vendor invoice.

Alternatively, you can also create a Vendor Invoice, by going to **Accounts Payable** \> **Invoices** \> **Open Vendor Invoices \> New** 

On posting the Vendor invoice, the invoice becomes available in Dataverse for project manager's verification and processing. 

## Vendor invoice processing in Dataverse

The Vendor invoice is created in Dataverse with some fields from the vendor invoice recorded in Finance and some defaulting from the subcontract.  

The following fields and related records will be copied from the subcontract to the header of the vendor invoice:
- Currency
- Contracting unit
- Payment terms

On the Vendor invoice line, Project operations uses the following field values to default the subcontract and subcontract line reference:
- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task

>[!NOTE] 
>Fixed price subcontract lines are not supported in Project Operations.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
