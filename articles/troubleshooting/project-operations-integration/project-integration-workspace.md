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

This workspace streamlines troubleshooting and configuration reviews by surfacing errors, system issues, and other potential problems that might otherwise remain hidden in logs. It is designed to save time and enhance visibility into critical processes. 
For instance, the workspace allows customers to identify and resolve Dual Write synchronization issues specifically related to vendor invoices and expenses. It provides detailed insights into error root causes, including the number of affected records and associated amounts, ensuring users have a comprehensive understanding of the issue's scope.

Key new capabilities include:  
- **Enhanced Dashboard for Accountants**: Highlights pending journal postings, missing integration journal lines, and records, simplifying ledger reconciliation.  
- **Batch Resynchronization Process**: A new batch process enables users to resynchronize data, effectively addressing and resolving inconsistencies to maintain data integrity and operational continuity.  
- **Detailed Document Sync View**: Provides a comprehensive view of documents like expense reports and vendor invoices, indicating their synchronization status between Dataverse and the finance and operations infrastructure.  
- **Comprehensive Troubleshooting Logs**: Offers full access to logs for the integration journal and invoice proposals, ensuring no data is truncated, enabling detailed troubleshooting and analysis.

## Prerequisites
To use the functionality, in **Dynamics 365 Finance**, activate the **Project Operations integration workspace** feature.

### Minimum versions required

To use the feature for Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios, you must have the following versions:

- **Project Operations Dataverse** version 4.122.0.690 or later.
- **Dynamics 365 Finance** version 10.0.43 or later.

## Dual Write
In Dynamics 365 Project Operations, when an expense or vendor invoice is posted, the financials are recorded in the procurement or expense integration account, while the project cost is posted using the project integration journal. However, accountants may encounter challenges when generating a trial balance for a period and finding balances in the expense or procurement integration accounts without a clear explanation. 

The Dual Write tab helps address this issue by providing insights into the causes of integration balance discrepancies. It highlights any issues affecting these balances and offers guidance on resolving them, making it easier to identify and correct discrepancies efficiently.

The unreconciled amounts section shows the outstanding balances for vendor invoices and expenses that have not yet been reconciled.
### Summary
The summary tab provides an overview of unreconciled amounts for expenses and vendor invoices. It includes detailed information such as amounts for which integration journal lines have not yet been created or posted, as well as records that are not synchronized from Dataverse to Dynamics 365 Finance.

### Expenses
The expense tab provides a detailed view of each expense record within the specified start and end dates. The following views can be validated:  

1. **Missing Actuals**: Displays expenses successfully processed in Dynamics 365 Finance but lacking reference records from Dataverse. Possible reasons include:  
   - Expenses not synchronized from Dynamics 365 Finance to Dataverse.  
   - Expenses not auto-approved in Dataverse.  
   - Actual records not synced from Dataverse to Dynamics 365 Finance.
2. **Missing Journal Lines**: Displays expenses that have been successfully processed and synchronized from Dataverse to Dynamics 365 Finance but for which integration journal lines have not yet been created or posted.
  
   To resolve this issue, you can execute the *Import from Staging* process from the periodic section or post the existing journals that are in draft status. 

3. **All Expenses**: Displays all expense records that have been successfully approved in Dynamics 365 Finance, regardless of whether the project cost has been updated through the project integration journal.
4. **All Reconciled Expenses**: Displays all expense records that have been successfully processed and project cost has been updated through the project integration journal.

### Vendor invoices
The vendor invoice tab provides a detailed view of each expense record within the specified start and end dates. The following views can be validated:  

1. **Missing Actuals**: Displays vendor invoice lines successfully processed in Dynamics 365 Finance but lacking reference records from Dataverse. Possible reasons include:  
   - Vendor invoices not synchronized from Dynamics 365 Finance to Dataverse.  
   - Vendor invoices not auto confirmed in Dataverse.  
   - Actual records not synced from Dataverse to Dynamics 365 Finance.
2. **Missing Journal Lines**: Displays Vendor invoices that have been successfully processed and synchronized from Dataverse to Dynamics 365 Finance but for which integration journal lines have not yet been created or posted.
  
   To resolve this issue, you can execute the *Import from Staging* process from the periodic section or post the existing journals that are in draft status. 

3. **All Vendor invoices**: Displays all Vendor invoice records that have been successfully approved in Dynamics 365 Finance, regardless of whether the project cost has been updated through the project integration journal.
4. **All Reconciled Vendor invoices**: Displays all Vendor invoice records that have been successfully processed and project cost has been updated through the project integration journal.

### Sync batch job
Dual write maps
## Troubleshooting
