---
title: Purchase non-stocked materials or procurement categories using a pending vendor invoice
description: This article explains how to record pending vendor invoices. 
author: mukumarm
ms.author: mukumarm
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Purchase nonstocked materials or procurement categories by using a pending vendor invoice

_**Applies To:** Project Operations Integrated with ERP_

When your company procures nonstocked materials or procurement categories for a project, you can immediately record the costs against the project. 

For example, Contoso Robotics US is performing an equipment renewal project and needs software licenses. The company procures these licenses from a third-party vendor. When you use Dynamics 365 Finance, the accounts payable clerk records a pending vendor invoice and attributes the license costs directly against the equipment renewal project. 

> [!IMPORTANT]
> Before you use the functionality described in this article, review and apply the required configurations. For more information, see [Enable nonstocked materials and pending vendor invoices](configure-materials-nonstocked.md) and [Use procurement categories with project purchase orders and pending vendor invoices](configure-procurement-categories.md).

## Post a project-related pending vendor invoice 

You can record pending vendor invoices on the **Pending vendor invoices** page (**Accounts payable** > **Invoices** > **Pending vendor invoices**). Complete the following steps to post a project-related pending vendor invoice:

1. Go to **Accounts payable** > **Invoices**, and select **New**. 
1. In the **Invoice account** field, select a vendor. In the **Number** field, enter the vendor invoice identification.
1. Add a line to the vendor invoice. In the **Item number** field, select the nonstocked item that you purchased from the vendor. Alternatively, in the **Procurement category** field, select the procurement category that you purchased from the vendor.   
1. Add the quantity that you purchased. The system fills in the unit price, based on the nonstocked item price configuration. 
1. Verify the total amount and other required details on the line.
1. In the line details, on the **Project** tab, select the ID of the project that this item is recorded to.
1. Optional: Select the activity number, and update the project category and line property.
1. Post the pending vendor invoice. When you post the invoice, the system records the following information:
    
    - The vendor balance amount.
    - The sales tax amount.
    - The cost against the project is recorded to the procurement integration account.
    - The project actual cost transaction in Dataverse. This transaction is further processed by using the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md). Posting this journal moves the amount from the procurement integration account to the project cost account. 
    - Purchases that are billed to the project customer by using the time and materials billing method. Additionally, unbilled sales transactions are created for the purchases in Dataverse. The product pricelist in Dataverse is used for the sales prices and amounts for unbilled sales transaction.
