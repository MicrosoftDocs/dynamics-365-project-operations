---
title: Project invoice integration
description: This article provides information about Project Operations dual-write integration for customer invoicing.
author: ryansandness
ms.author: ryansandness
ms.date: 02/27/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project invoice integration

[!INCLUDE[banner](../includes/banner.md)]

This article provides information about Project Operations dual-write integration for customer invoicing.

In Project Operations, the Project manager manages the project billing backlog and creates a proforma invoice for the customer in Microsoft Dataverse. Based on this proforma invoice, the Accounts receivable clerk or Project accountant creates a customer-facing invoice. Dual-write integration ensures that the proforma invoice details are synchronized to finance and operations apps. After the customer-facing invoice is posted, the system updates the relevant project actuals in Dataverse with the accounting detail. The following graphic provides a high-level conceptual overview of this integration.

   :::image type="content" source="./media/DW5Invoicing.png" alt-text="Screenshot of Project invoice integration.":::

After the Project manager confirms the proforma invoice in Dataverse, the proforma invoice header information synchronizes to finance and operations apps using the dual-write table map, **Project invoice proposal V2 (invoices)**. This is a one-way integration from Dataverse to finance and operations apps. Creating or deleting Project invoice proposals directly in finance and operations apps isn't supported.

Invoice confirmation in Dataverse also triggers the business logic to create billing-related records in the **Actuals** entity. These records are synchronized to finance and operations using the dual-write table map, **Project Operations integration actuals (msdyn\_actuals).** For more information, see [Project estimates and actuals](resource-dual-write-estimates-actuals.md). 

Project invoice proposal lines are created by the periodic process, **Import form staging**. This process is based on the billed sales actuals details in the **Actuals staging** table. For more information, see [Manage project invoice proposals](../invoicing/format-update-project-invoice-proposals.md#create-project-invoice-proposals). 
