---
title: Project Operations integration workspace
description: Learn about the Project Operations integration workspace, which helps identify and address integration challenges that are related to vendor invoices and expenses.
author: mukumarm
ms.date: 01/27/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Project Operations integration workspace

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article provides information about the **Project Operations integration** workspace. This workspace helps you identify and address integration challenges that are related to vendor invoices and expenses. To help with troubleshooting, it also lets you access complete logs for the integration journal and invoice proposals.

The **Project Operations integration** workspace streamlines troubleshooting and configuration reviews by revealing errors, system issues, and other potential issues that might otherwise remain hidden in logs. The workspace is designed to help save time and enhance visibility into critical processes. For example, you can identify and fix dual-write synchronization issues that are related to vendor invoices and expenses. The workspace provides detailed insights into the root causes of errors, including the number of affected records and associated amounts. Therefore, you gain a comprehensive understanding of the scope of an issue.

Here are some of the new capabilities:

- **Enhanced dashboard for accountants** – The dashboard simplifies ledger reconciliation by highlighting pending journal postings, missing integration journal lines, and records. 
- **Batch resynchronization process** – A new batch process lets you resync data. In this way, you can effectively address and fix inconsistencies, and maintain data integrity and operational continuity.
- **Detailed document synchronization view** – You can get a comprehensive view of documents such as expense reports and vendor invoices, including the status of their synchronization between Microsoft Dataverse and the finance and operations apps infrastructure.
- **Comprehensive troubleshooting logs** – You get full access to logs for the integration journal and invoice proposals. You can use these logs to ensure that no data is truncated. In this way, the logs allow for detailed troubleshooting and analysis.

## Prerequisites

To use the functionality, activate the **Project Operations integration workspace** feature in Dynamics 365 Finance.

### Minimum versions required

To use the feature for Dynamics 365 Project Operations for resource/non-stocked based scenarios, you must have the following versions:

- Project Operations Dataverse version 4.124.0.690 or later
- Finance version 10.0.43 or later

## Use the Dual-write tab

When an expense or a vendor invoice is posted in Project Operations, the financials are recorded in the procurement or expense integration account. The project cost is posted by using the project integration journal. However, when accountants generate a trial balance for a period, they might encounter challenges. For example, they might find balances in the procurement or expense or integration account without a clear explanation.

The **Dual-write** tab of the **Project Operations integration** workspace helps address this issue by providing insights into the causes of discrepancies in integration balances. Issues that affect these balances are highlighted, and guidance for resolving them is offered. Therefore, it's easier to identify and correct discrepancies efficiently.

The **Unreconciled amounts** FastTab on the **Dual-write** tab shows the outstanding balances for vendor invoices and expenses that haven't yet been reconciled.

The **Categories** FastTab has three tabs: **Summary**, **Expense**, and **Vendor invoice lines**.

### Use the Summary tab

The **Summary** tab on the **Categories** FastTab provides an overview of unreconciled amounts for expenses and vendor invoices. It includes detailed information such as amounts that project integration journal lines aren't yet created or posted for, and records that aren't synced from Dataverse to Finance.

![Screenshot that shows the Summary tab in the Project Operations integration workspace.](../../../articles/media/ProjOpsIntegrationWorkspaceSummary.png)

### Use the Expense tab

The **Expense** tab provides a detailed view of each expense record within the specified start and end dates. The start date is the first open ledger period, based on the current year and previous year that are associated with the company. The end date is the current date.

The following views can be validated:

- **Missing actuals** – This view shows expenses that were successfully processed in Finance, but that lack reference records from Dataverse. There are several possible reasons for this issue:

    - Expenses weren't synced from Finance to Dataverse.
    - Expenses weren't automatically approved in Dataverse.
    - Actual records weren't synced from Dataverse to Finance.

- **Missing journal lines** – This view shows expenses that were successfully processed and synced from Dataverse to Finance, but that integration journal lines aren't yet created or posted for.

    To fix this issue, you can run the **Import from Staging** process from the **Periodic** section. Alternatively, you can post the existing journals that are in draft status.

- **All expenses** – This view shows all expense records that were successfully approved in Finance, regardless of whether the project cost was updated through the project integration journal.
- **All reconciled expenses** – This view shows all expense records that were successfully processed, and that project cost was updated for through the project integration journal.

To reprocess any expenses that weren't synced earlier because of dual-write failures, you can use the **Sync** button at the top of the grid to run the synchronization batch job. This job syncs all expenses, based on the first open period of the fiscal calendar and the current date. Learn more in the [Run the synchronization batch job](#run-the-synchronization-batch-job) section.

![Screenshot that shows the Missing actuals view of the Expense tab in the Project Operations integration workspace.](../../../articles/media/ProjOpsIntegrationWorkspaceexpense.png)

### Use the Vendor invoice lines tab

The **Vendor invoice lines** tab provides a detailed view of each vendor invoice line record within the specified start and end dates. The start date is the first open ledger period, based on the current year and previous year that are associated with the company. The end date is the current date.

The following views can be validated:

- **Missing actuals** – This view shows vendor invoice lines that were successfully processed in Finance, but that lack reference records from Dataverse. There are several possible reasons for this issue:

    - Vendor invoices weren't synced from Finance to Dataverse.
    - Vendor invoices weren't automatically confirmed in Dataverse.
    - Actual records weren't synced from Dataverse to Finance.

- **Missing journal lines** – This view shows vendor invoices that were successfully processed and synced from Dataverse to Finance, but that integration journal lines aren't yet created or posted for.

    To fix this issue, you can run the **Import from Staging** process from the **Periodic** section. Alternatively, you can post the existing journals that are in draft status.

- **All vendor invoices** – This view shows all vendor invoice records that were successfully approved in Finance, regardless of whether the project cost was updated through the project integration journal.
- **All reconciled vendor invoices** – This view shows all vendor invoice records that were successfully processed, and that project cost were updated for through the project integration journal.

To reprocess any vendor invoices that weren't synced earlier because of dual-write failures, you can use the **Sync** button at the top of the grid to run the synchronization batch job. This job syncs all vendor invoices, based on the first open period of the fiscal calendar and the current date. Learn more in the [Run the synchronization batch job](#run-the-synchronization-batch-job) section.

![Screenshot that shows the Missing actuals view being selected on the Vendor invoice lines tab of the Project Opertaions integration workspace.](../../../articles/media/ProjOpsIntegrationWorkspaceVendorInvoice.png)

### Run the synchronization batch job

In some cases, expenses and vendor invoices are successfully processed in Finance, but they aren't synced with Dataverse because of dual-write issues. This mismatch is one reason why procurement or integration accounts aren't nullified, so that a balance remains in them.

To address this issue and ensure synchronization of expenses or vendor invoices that weren't previously synced, a new batch job is added. This batch job can be run on a recurring basis at the end of each day to ensure that it processes a minimal set of records. The start date is the first open ledger period, based on the current year and previous year that are associated with the company. The end date is the current date.

To run the synchronization batch job, go to **Project management and accounting** \> **Periodic** \> **Project operations reconciliation**.

To use the batch job, you must use the following dual-write map versions.

| Required dual-write map | Required version |
|---|---|
| Project Operations integration project expenses export entity (msdyn_expenses) | 1.0.0.5 |
| Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices) | 1.0.0.1 |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.8 |

## Use the Troubleshoot tab

The **Troubleshoot** tab shows a list of error messages that users encountered during the **Import from staging** or **Project integration journal** posting processes. This tab helps you identify the root cause of issues, so that you can make the necessary corrections. You can filter the records by specifying **From Date** and **To Date** values. After corrections are completed, you can use the **Delete** or **Delete All** button to delete messages that are no longer needed.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
