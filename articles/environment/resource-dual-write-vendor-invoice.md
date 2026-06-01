---
title: Vendor invoice integration
description: Learn how to integrate vendor invoices in Dynamics 365 Project Operations, including posting rules, dual-write synchronization, and intercompany invoice support.
author: mukumarm
ms.date: 02/05/2026
ms.reviewer: johnmichalak
ms.author: mukumarm
ms.topic: concept-article
ms.custom: 
  - bap-template
---

# Vendor invoice integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

You can record project-related procurement in Dynamics 365 Project Operations by going to **Accounts Payable** > **Invoices** > **Pending vendor invoices** and using a pending vendor invoice document. For more information, see [Purchase non-stocked materials using a pending vendor invoice](../procurement/pending-vendor-invoices.md).

> [!IMPORTANT]
> Before you use the functionality described in this article, review and apply the required configurations. For more information, see [Enable non-stocked materials and pending vendor invoices](../procurement/configure-materials-nonstocked.md).

In Project Operations, post project-related vendor invoices by using special posting rules:

- The process doesn't immediately post project-related cost (including non-recoverable tax) to the project cost account in the general ledger. Instead, it posts the cost to the **Procurement integration account**. You can configure this account in **Project management and accounting** > **Setup** > **Project management and accounting parameters** on the **Project Operations on Dynamics 365 Customer engagement** tab.
- Dual-write synchronizes vendor invoice details to Microsoft Dataverse by using the following table maps:

  - **Project Operations integration project vendor invoice export entity (msdyn_projectvendorinvoices)**: This table map synchronizes vendor invoice header information. Only vendor invoices with at least one line that contains a project ID are synchronized to Dataverse.
  - **Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines)**: This table map synchronizes vendor invoice line information. Only lines that contain a project ID are synchronized to Dataverse.

## Vendor invoice lines

As part of the 10.0.38 upgrade, a new iteration of the dual-write map, version 1.0.0.6, is introduced specifically for vendor invoice lines. This updated version enables the execution of intercompany vendor invoices. To enable this feature, some integration keys are modified. If the dual-write map for vendor invoice lines stops working, follow these steps:

1. In the **Data Management** workspace, go to the **Dual Write Maps** section.
1. On the Action Pane, select **Integration key**.
1. Select the **project vendor invoice line** integration key.
1. Remove the **msdyn\_owningcompany** field from the integration key.
1. Ensure that **msdyn\_externalinvoiceline** remains the only field for the integration key.

> [!NOTE]
> Vendor invoices aren't editable in Dataverse.

When you post a vendor invoice, Dynamics 365 Finance records tax subledger, vendor subledger, and other financial postings as applicable.

:::image type="content" source="media/DW7VendorInvoice.png" alt-text="Screenshot of the vendor invoice integration flow diagram.":::

When you write records to a **Vendor invoice** entity in Dataverse, an automated approval process of the records begins. If needed, you can review the automated approval process status in Dataverse by going to **Advanced settings** > **System** > **System jobs**. After the approval is complete, the system creates material transaction class records in the **Actuals** entity.

Material-related actuals are then processed using the dual-write table map, **Project Operations integration actuals (msdyn_actuals)**. For more information, see [Project estimates and actuals](resource-dual-write-estimates-actuals.md).

The periodic process, **Import from staging** creates vendor invoice-related Project Operations integration journal lines. The offset account defaults to the procurement integration account. When you post the integration journal, the account balance clears for the vendor invoice transaction and the line amount moves to the project cost account. Project subledger transactions are also created for downstream invoicing and revenue recognition purposes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
