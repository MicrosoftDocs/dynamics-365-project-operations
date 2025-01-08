---
title: Project operations integration workspace
description: This article helps identify integration challenges related to vendor invoices and expenses while offering strategies to address them. It also includes a troubleshooting guide, enabling access to complete logs of the integration journal and invoice proposals.
author: mukumarm
ms.date: 01/27/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Project operations integration workspace

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article helps identify integration challenges related to vendor invoices and expenses while offering strategies to address them. It also includes a troubleshooting guide, enabling access to complete logs of the integration journal and invoice proposals.

The integration workspace streamlines troubleshooting and configuration reviews by surfacing errors, system issues, and other potential problems that might otherwise remain hidden in logs. The workspace is designed to save time and enhance visibility into critical processes. For example, the workspace allows you to identify and resolve Dual-write synchronization issues related to vendor invoices and expenses. It provides detailed insights into error root causes, including the number of affected records and associated amounts, ensuring users have a comprehensive understanding of the issue's scope.

New capabilities include:  
- **Enhanced Dashboard for Accountants**: Highlights pending journal postings, missing integration journal lines, and records to simplify ledger reconciliation. 
- **Batch Resynchronization Process**: A new batch process enables you to resynchronize data to effectively address and resolve inconsistencies, and maintain data integrity and operational continuity.  
- **Detailed Document Sync View**: Provides a comprehensive view of documents, like expense reports and vendor invoices, indicating their synchronization status between Dataverse and the finance and operations apps infrastructure.  
- **Comprehensive Troubleshooting Logs**: Offers full access to logs for the integration journal and invoice proposals, ensuring no data is truncated to enable detailed troubleshooting and analysis.

## Prerequisites

To use the functionality, in Microsoft Dynamics 365 Finance, activate the **Project Operations integration workspace** feature.

### Minimum versions required

To use the feature for Dynamics 365 Project Operations for resource/non-stocked based scenarios, you must have the following versions:

- **Project Operations Dataverse** version 4.124.0.690 or later.
- **Dynamics 365 Finance** version 10.0.43 or later.

## Use the Dual-write tab

When an expense or vendor invoice is posted in Project Operations, the financials are recorded in the procurement or expense integration account, while the project cost is posted using the project integration journal. However, accountants might encounter challenges when generating a trial balance for a period, and might find balances in the expense or procurement integration accounts without a clear explanation. 

The **Dual-write** tab helps address this issue by providing insights into the causes of integration balance discrepancies. Issues affecting these balances are highlighted, and guidance for resolving them is offered to make it easier to identify and correct discrepancies efficiently.

The **unreconciled amounts** section shows the **outstanding balances** for **vendor invoices** and **expenses** that haven't yet been reconciled.

### Use the Summary tab

The **Summary** tab provides an overview of unreconciled amounts for expenses and vendor invoices. It includes detailed information such as amounts for which project integration journal lines aren't yet created or posted, and records that aren't synchronized from Dataverse to Dynamics 365 Finance.

![Project integration workspace summary.](../../../articles/media/ProjOpsIntegrationWorkspaceSummary.png)

### Use the Expenses tab

The **Expense** tab provides a detailed view of each expense record within the specified start and end dates. The **Start date** is the first open ledger period based on the current and previous year associated with the company, while the **End date** is the current date.

The following views can be validated using the **Expense** tab:  

1. **Missing Actuals**: Displays expenses successfully processed in Dynamics 365 Finance but lacking reference records from Dataverse. Possible reasons include:  
   - Expenses not synchronized from Dynamics 365 Finance to Dataverse. 
   - Expenses not autoapproved in Dataverse.  
   - Actual records not synced from Dataverse to Dynamics 365 Finance.

1. **Missing Journal Lines**: Displays expenses that were successfully processed and synchronized from Dataverse to Dynamics 365 Finance but for which integration journal lines aren't yet created or posted.
  
   To resolve this issue, you can run the *Import from Staging* process from the periodic section or post the existing journals that are in draft status. 

1. **All Expenses**: Displays all expense records that were successfully approved in Dynamics 365 Finance, regardless of whether the project cost was updated through the project integration journal.

1. **All Reconciled Expenses**: Displays all expense records that were successfully processed, and project cost was updated through the project integration journal.

The **Sync button** at the top of the grid enables you to run the **synchronization batch job** to reprocess **expenses** that weren't **synchronized** earlier due to **Dual-write failures**. It **synchronizes** all expenses based on the **first open period** of the fiscal calendar and the **current date**. For more information, see [Sync batch job](project-integration-workspace.md#sync-batch-job).

![Project integration workspace expenses.](../../../articles/media/ProjOpsIntegrationWorkspaceexpense.png)

### Use the Vendor invoices tab

The **vendor invoice** tab provides a detailed view of each vendor invoice line record within the specified start and end dates. The **Start date** is the first open ledger period based on the current and previous year associated with the company, while the **End date** is the current date.

The following views can be validated:  

1. **Missing Actuals**: Displays vendor invoice lines successfully processed in Dynamics 365 Finance but lacking reference records from Dataverse. Possible reasons include:

   - Vendor invoices not synchronized from Dynamics 365 Finance to Dataverse.  
   - Vendor invoices not autoconfirmed in Dataverse.  
   - Actual records not synced from Dataverse to Dynamics 365 Finance.
    
1. **Missing Journal Lines**: Displays Vendor invoices that were successfully processed and synchronized from Dataverse to Dynamics 365 Finance but for which integration journal lines aren't yet created or posted.
  
   To resolve this issue, you can run the *Import from Staging* process from the periodic section or post the existing journals that are in draft status. 

1. **All Vendor invoices**: Displays all Vendor invoice records that were successfully approved in Dynamics 365 Finance, regardless of whether the project cost was updated through the project integration journal.

1. **All Reconciled Vendor invoices**: Displays all Vendor invoice records that were successfully processed and project cost were updated through the project integration journal.

The **Sync button** at the top of the grid enables you to run the **synchronization batch job** to reprocess **expenses** that weren't **synchronized** earlier due to **Dual-write failures**. It **synchronizes** all expenses based on the **first open period** of the fiscal calendar and the **current date**. For more information, see [Sync batch job](project-integration-workspace.md#sync-batch-job).

![Project integration workspace vendor invoices.](../../../articles/media/ProjOpsIntegrationWorkspaceVendorInvoice.png)

### Sync batch job

There are instances where expenses and vendor invoices are successfully processed in Dynamics 365 Finance but fail to synchronize with Dataverse due to Dual-write issues. This mismatch is one of the reasons that procurement or integration accounts aren't being nullified, causing a balance to remain in these accounts.

To address this issue and ensure that expenses or vendor invoices are synchronized if they weren't previously, a new batch job has been added. This batch job can be run on a recurring basis at the end of each day to ensure it processes a minimal set of records. The **Start date** is the first open ledger period based on the current and previous year associated with the company, while the **End date** is the current date.

To run sync batch job, follow this step.

Go to **Project management and accounting** \> **Periodic** \> **Project operations reconciliation**.

To use the project operations reconciliation batch job, use the below Dual-write map versions.

| Required Dual-write map | Required version |
|---|---|
| Project Operations integration project expenses export entity (msdyn_expenses) | 1.0.0.5 |
| Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices) | 1.0.0.1 |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.8 |

## Troubleshooting

The **Troubleshoot** tab displays a list of error messages encountered by users during the **Import from staging** or **Project integration journal** posting processes. This tab helps you identify the root cause of issues so you can make the necessary corrections. Records can be filtered by specifying a **From Date** and **To Date**. Once corrections are complete and the messages are no longer needed and can be deleted using the **Delete** or the **Delete All** button.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
