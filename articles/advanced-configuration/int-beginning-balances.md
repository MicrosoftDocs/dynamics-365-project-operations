---
title: Manage beginning balances for Project Operations integrated deployments
description: Learn how to manage and import beginning or opening balances into Microsoft Dynamics 365 Project Operations integrated with ERP.
author: mukumarm
ms.date: 09/22/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage beginning balances for Project Operations integrated with ERP deployments

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations integrated with ERP deployments._

**Beginning balances**, also called **opening balances**, are transactions incurred outside **Dynamics 365 Project Operations** before the project is set up in the system. These balances typically arise in scenarios such as:

* Migrating from a legacy ERP system
* Previously maintaining financial records by using other tools or manual processes

When you move to **Dynamics 365 Project Operations**, bring forward opening balances for projects, customers, and related financial data to keep continuity and accurate reporting. 
This process sets initial values for costs, revenue, work in progress (WIP), and billing.

This article shows how to manage or import project opening balances in Microsoft Dynamics 365 Project Operations. The feature integrates with Dynamics 365 Finance. 

## Prerequisites
### Feature

Activate the following feature:
- **Enable beginning balances in Project Operations Integrated with ERP** in Dynamics 365 Finance

### Minimum version required

For Project Operations integrated deployments, use the following version:
- **Dynamics 365 Finance** 10.0.46 or later

## Import beginning balances
New customers implementing Project Operations need to enter beginning balances for in-progress projects. For the integrated Project Operations scenario, the system can generate beginning balance amounts based on actuals as of a **specified date**. 
This date is the **cut-off date** and assumes that the **General ledger** is already updated. 
This ensures the **fixed price revenue recognition** process calculates correctly. 
After the balances are integrated and posted, run the **revenue recognition** process for the beginning balances. 

### Project management and accounting parameters
To create **beginning balances** as of a **specified date**, follow these steps:

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1. In the **General** tab, select **Create beginning balances**.
1. In the **As of date**, enter the cut-off date.
1. Select the beginning balance journal name.

> [!NOTE]
> The **Cut-off date** field becomes **non-editable** after the first transaction is posted using the **Beginning Balance journal**.
> 
### Import beginning balances

When **Actuals** are imported into **Dynamics 365 Finance** from **Dynamics 365 Project operations** on or before the specified **As of date**, the system creates **Beginning Balance journal** lines instead of project operations **integration journal** lines.

Beginning balance journals don't generate accounting entries in the general ledger. They only update the project subledger for tracking.

To generate the beginning balances in **Dynamics 365 Finance**, follow these steps:
1. Go to **Project management and accounting** > **Periodic** > **Project operations integration** > **Import beginning balances**.
1. Select **Ok** to generate the beginning balance journal.

> [!NOTE]
> Any transaction generated in Project Operations actuals after the **cut-off date** is imported through the **Import from staging** process and processed using the **Project Operations integration journal**.
> 
### Beginning balance journal
After you run the **Import beginning balances** process, the system creates a **Beginning balance journal** along with its journal lines.
All actual transactions in **Project Operations** that have a transaction date on or before the defined **cut-off date** are included in this journal to establish the opening balances.

To view and post the beginning balance journal, follow these steps:
1. Go to **Project management and accounting** > **Journals** > **Beginning balance**.
1. Select **Lines**.
1. Select **Post** to post the beginning balance journal.

The system generates the **project subledger** immediately after posting the project balance journal, as shown in the following table:

|Contract line|Project transaction|Project transaction posting|
|--|--|--|
|Time & Material|Project cost|Profit and loss|
|Time & Material|Unbilled sales|Project cost and revenue profile rule|
|Time & Material|Billed sales|Profit and loss|
|Fixed price|Project cost|Project cost and revenue profile rule|
|None|Project cost|Profit and loss|

> [!NOTE]
> Project operations journals are the best way to upload the beginning balances, and actuals generate once the journals are confirmed. These actuals generate **beginning balance journals** in **Dynamics 365 Finance**.
> 
> The beginning balance journal posting process doesn't generate financial transactions and only generates the project subledger.
> 
> **Billed Milestones and retainers** aren't currently supported in this process and are planned for a future release. 
