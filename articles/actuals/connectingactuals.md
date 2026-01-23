---
title: Transaction connections - Link actuals of different transaction types
description: This article explains how a transaction connection is used to link actuals of different types to help track profitability, billing backlog, and billed versus unbilled revenue calculations.
author: suvaidya
ms.date: 01/23/2026
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Transaction connections - Link actuals of different transaction types

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Create transaction connection records to link actuals of different types, such as time, expense, or material usage. These connections track the lifecycle of actuals as they move from the quote or pre-sales stage to the contract stage, through approvals and recalls, invoicing, and potentially credit or corrective invoicing.

The following example shows the typical processing of time entries in a Project Operations project lifecycle.

:::image type="content" source="media/basic-guide-17.png" alt-text="Screenshot of processing time entries in Project Operations.":::

The processing of time entries in a Project Operations project lifecycle follows these steps: 

1. Submission of a time entry creates two journal lines: one for cost and one for unbilled sales. 
1. Approval of the time entry creates two actuals: one for cost and one for unbilled sales. These two actuals link together by using transaction connections.
1. When the user creates a project invoice, the system uses data from the unbilled sales actual to create the invoice line transaction.
1. When the user confirms the invoice, the system creates two new actuals: an unbilled sales reversal and a billed sales actual. The unbilled sales reversal and the original unbilled sales actual connect by using reversing transaction connections. The billed sales and the original unbilled sales actual also connect to show the links between what was once backlog or work in progress (WIP) revenue to what is now billed revenue.   

Each event in the processing workflow triggers the creation of records in the **Transaction connection** table. This process helps to build a trace of the relationships between the records that are created across time entry, journal line, actual, and invoice line details.

The following table shows the records in the **Transaction connection** entity for the preceding workflow.

|Event                   |Transaction 1                 |Transaction 1 role |Transaction 1 type       |Transaction 2          |Transaction 2 role |Transaction 2 type |
|------------------------|------------------------------|---------------|-----------------------------|-----------------------------|-------------------|-------------------|
|Time Entry Submission   |Journal Line (Sales) GUID     |Unbilled Sales |msdyn_journalline            |Journal Line (cost) GUID     |Cost            |msdyn_journalline  |
|Time Approval           |Unbilled Actual (Sales) GUID  |Unbilled Sales |msdyn_actual                 |Cost Actual(cost) GUID       |Cost            |msdyn_actual       |
|Invoice Creation        |Invoice Line Detail GUID      |Billed Sales   |msdyn_invoicelinetransaction |Unbilled Sales Actual GUID   |Unbilled Sales  |msdyn_actual       |
|Invoice Confirmation    |Reversing Actual GUID         |Reversing      |msdyn_actual                 |Original unbilled sales GUID |Original        |msdyn_actual       |
|                        |Billed Sales GUID             |Billed Sales   |msdyn_actual                 |Unbilled Sales Actual GUID   |Unbilled Sales  |msdyn_actual       |
|Draft Invoice Correction |Invoice Line Transaction GUID|Replacing      |msdyn_invoicelinetransaction |Billed Sales GUID            |Original        |msdyn_actual       |
|Confirm Invoice Correction|Billed Sales Reversal GUID  |Reversing      |msdyn_actual                 |Billed Sales GUID            |Original        |msdyn_actual       |
|                        |New Unbilled Sales GUID |Replacing            |msdyn_actual                 |Billed Sales GUID            |Original        |msdyn_actual       |


The following illustration shows the links that are created between different types of actuals at various events by using the example of time entries in Project Operations.

:::image type="content" source="media/TransactionConnections.png" alt-text="Screenshot of how actuals of different types are linked to each other in Project Operations.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
