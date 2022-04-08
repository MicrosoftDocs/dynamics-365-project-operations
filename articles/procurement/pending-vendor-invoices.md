---
title: Purchase non-stocked materials or procurement categories using a pending vendor invoice
description: This topic explains how to record pending vendor invoices. 
author: sigitac
ms.date: 09/13/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# Purchase non-stocked materials or procurement categories using a pending vendor invoice

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

As a company procures non-stocked materials or procurement categories for a project, the costs can be immediately recorded against the project. 

For example, Contoso Robotics US is performing an equipment renewal project and needs software licenses. These licenses are procured from a third-party vendor.  Using Dynamics 365 Finance, the Accounts payable clerk records a pending vendor invoice document and attributes the license costs directly against the equipment renewal project. 

> [!IMPORTANT]
> Before you use the functionality described in this topic, review and apply the required configurations. For more information, see [Enable non-stocked materials and pending vendor invoices](configure-materials-nonstocked.md) and [Use procurement categories with project purchase orders and pending vendor invoices].(configure_procurement-categories.md)

## Post a project-related pending vendor invoice 

Pending vendor invoices can be recorded on the **Pending vendor invoices** page (**Accounts payable** > **Invoices** > **Pending vendor invoices**). Complete the following steps to post a project-related pending vendor invoice:

1. Go to **Accounts payable** > **Invoices** and select **New**. 
2. In the **Invoice account** field, select a vendor and in the **Number** field, enter the vendor invoice identification.
3. Add a line to the vendor invoice and in the **Item number** field, select the non-stocked item purchased from the vendor or alternatively select **Procurement category** to be purchased from the vendor.   
4. Add the quantity purchased. The system will populate the unit price based on the non-stocked item price configuration. 
5. Verify the total amount and other required details on the line.
6. On the line details, on the **Project** tab, select the ID of the project that this item will be recorded to.
7. Optionally, select the activity number, and update the project category and line property.
8. Post pending vendor invoice. When the invoice is posted, the system records:
    
    - The vendor balance amount.
    - The sales tax amount.
    - The cost against the project is recorded to the procurement integration account.
    - The project actual cost transaction in Dataverse.  This transaction is further processed using the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md). Posting this journal moves the amount from the procurement integration account to the project cost account. 
    - Purchases that are billed to the project customer using the time and materials billing method. Additionally, unbilled sales transactions are created for the purchases in Dataverse. The product pricelist in Dataverse is used for the sales prices and amounts for unbilled sales transaction.
