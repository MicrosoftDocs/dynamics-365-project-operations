---
title: Use actuals synchronization and reconciliation
description: Learn about the Project Operations actuals synchronization and reconciliation framework that helps identify and address integration challenges that are related to project actuals and transaction connection entities.
author: mukumarm
ms.date: 06/16/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
ms.search.form: ProjTroubleshootingWorkspace
---
# Use actuals synchronization and reconciliation

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article provides information about the **Project Operations Actuals Synchronization & Reconciliation** framework. This workspace helps you identify and address integration challenges that are related to project actuals and transaction connections. You can identify and fix dual-write synchronization issues that are related to Actuals or transaction connections. It also allows you to initiate a resynchronization of actuals or transaction connections, which in turn facilitates the generation and posting of integration journal lines.  

## Prerequisites

### Minimum versions required

To use the feature for Dynamics 365 Project Operations for resource/non-stocked based scenarios, you must have the following versions:

- Project Operations Dataverse version 4.142.0.x or later
- Microsoft Dynamics 365 Finance version 10.0.43 or later

### Dual write maps

|Required dual-write map | Required version |
|---|---|
|Project Operations integration actuals (msdyn_actuals) |1.0.0.20|
|Integrated entity for transaction relationships (msdyn_transactionconnections|1.0.0.1|

## Missing actuals

To resolve synchronization issues with actuals or transaction connections that were previously unsynced, a new form called **Out of sync actuals** is available in the **Settings section**. This form displays actuals for which the Project integration journal or project invoices aren't posted in Finance or actuals aren't synchronized to Finance and Project integration journal or project invoice lines aren't created for missing records.

A filter is applied to the **Actuals** entity to show only those records where **Skip sync** is true and **Voucher** is missing because each actual record should have a generated and posted a voucher. Currently, the form displays only those actuals that were generated at least one hour ago and are limited to transactions from the previous month.

To view the **Actuals** in **Project operations** that are yet to be processed in **Dynamics 365 Finance**, follow these steps.

1. Navigate to **Settings**.
1. Select **Out of sync Actuals** in the **Troubleshooting** area.
1. Review the displayed records. These actuals represent the records without a posted voucher.

> [!NOTE]
> This form displays and synchronizes actuals that are missing or not yet synchronized for the past month, with a one-hour delay. The delay accounts for the time required to complete processes such as integration journal creation or project invoice generation and posting.
 
### Sync missing actuals

If issues arise during the generation of the **Project operations integration journal** for **Actuals**, such as missing actuals or transaction connections in Finance you can resync the actuals or transaction connections to Finance. This helps ensure that the **Project Integration Journal** or **Project Invoices** are successfully created and processed.

To resync the actuals or transaction connections to Finance, use the **Sync Actuals** button available on the **Out of sync actuals** form. This action attempts to reprocess all records displayed on the form.

Because the **Project Operations Integration Journal** is posted in Finance on a recurring schedule, there may be cases where actuals are synchronized correctly, but the journal isn't yet posted. Therefore, it's recommended to **wait** for the posting of either the Project Operations Integration Journal or the Project Invoice before **restarting** the sync process.

![Screenshot that shows the Out of sync actuals in the Project Operations.](../media/out-of-sync-actuals.png)
