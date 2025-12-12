---
title: Purchase non-stocked materials or procurement categories using a pending vendor invoice
description: This article explains how to record pending vendor invoices. 
author: mukumarm
ms.author: mukumarm
ms.date: 07/26/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Purchase non-stocked materials or procurement categories using a pending vendor invoice

_**Applies To:** Project Operations Integrated with ERP_

As a company procures non-stocked materials or procurement categories for a project, the costs can be immediately recorded against the project. 

For example, Contoso Robotics US is performing an equipment renewal project and needs software licenses. These licenses are procured from a third-party vendor.  When you use Dynamics 365 Finance, the Accounts payable clerk records a pending vendor invoice document and attributes the license costs directly against the equipment renewal project. 

> [!IMPORTANT]
> Before you use the functionality described in this article, review and apply the required configurations. For more information, see [Enable non-stocked materials and pending vendor invoices](configure-materials-nonstocked.md) and [Use procurement categories with project purchase orders and pending vendor invoices](configure-procurement-categories.md)

## Post a project-related pending vendor invoice 

Pending vendor invoices can be recorded on the **Pending vendor invoices** page (**Accounts payable** > **Invoices** > **Pending vendor invoices**). Complete the following steps to post a project-related pending vendor invoice:

1. Go to **Accounts payable** > **Invoices**, and select **New**. 
1. In the **Invoice account** field, select a vendor, and then, in the **Number** field, enter the vendor invoice identification.
1. Add a line to the vendor invoice, and then, in the **Item number** field, select the non-stocked item that was purchased from the vendor. Alternatively, in the **Procurement category** field, select the procurement category that was purchased from the vendor.   
1. Add the quantity that was purchased. The system fills in the unit price, based on the non-stocked item price configuration. 
1. Verify the total amount and other required details on the line.
1. In the line details, on the **Project** tab, select the ID of the project that this item is recorded to.
1. Optional: Select the activity number, and update the project category and line property.
1. Post the pending vendor invoice. When the invoice is posted, the system records the following information:
    
    - The vendor balance amount.
    - The sales tax amount.
    - The cost against the project is recorded to the procurement integration account.
    - The project actual cost transaction in Dataverse.  This transaction is further processed using the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md). Posting this journal moves the amount from the procurement integration account to the project cost account. 
    - Purchases that are billed to the project customer using the time and materials billing method. Additionally, unbilled sales transactions are created for the purchases in Dataverse. The product pricelist in Dataverse is used for the sales prices and amounts for unbilled sales transaction.
