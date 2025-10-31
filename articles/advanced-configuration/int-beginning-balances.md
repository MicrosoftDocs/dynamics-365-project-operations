---
title: Manage beginning balances for Project Operations integrated deployments
description: Learn how to manage and import beginning or opening balances into Microsoft Dynamics 365 Project Operations integrated with ERP.
author: mukumarm
ms.date: 10/31/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage beginning balances for Project Operations integrated with ERP deployments

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations integrated with ERP deployments._

*Beginning balances*, also called *opening balances*, are transactions incurred outside Dynamics 365 Project Operations before you set up the project in the system. These balances typically arise in scenarios such as:

* Migrating from a legacy ERP system.
* Previously maintaining financial records by using other tools or manual processes.

Move opening balances for projects, customers, and related financial data into Project Operations to maintain continuity and accurate reporting. This process sets initial values for costs, revenue, work in progress (WIP), and billing.

Use this article to manage and import project opening balances in Project Operations. The feature integrates with Microsoft Dynamics 365 Finance. 

## Prerequisites
### Feature

Turn on the **Enable beginning balances in Project Operations Integrated with ERP** feature in Dynamics 365 Finance.

### Minimum version required

Use **Dynamics 365 Finance** version 10.0.46 or later for Project Operations integrated deployments.

## Import beginning balances

Enter beginning balances for in-progress projects when you implement Project Operations. In the integrated Project Operations scenario, the system generates beginning balance amounts from actuals as of a **specified date**. This date is the **cut-off date** and assumes the **General ledger** is updated. This setup ensures the **fixed price revenue recognition** process calculates correctly. After you integrate and post the balances, run the **revenue recognition** process for the beginning balances. 

### Project management and accounting parameters

To create **beginning balances** as of a **specified date**, follow these steps.

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1. On the **General** tab, select **Create beginning balances**.
1. In **As of date**, enter the cut-off date.
1. Select the beginning balance journal name.

> [!NOTE]
> The **Cut-off date** field becomes **non-editable** after the first transaction is posted using the **Beginning Balance journal**.

### Import beginning balances

When you import **Actuals** into Finance from Project operations on or before the **As of date**, the system creates **Beginning Balance journal** lines instead of Project Operations **integration journal** lines.

Beginning balance journals don't generate general ledger accounting entries; they only update the project subledger.

To generate the beginning balances in **Dynamics 365 Finance**, follow these steps.

1. Go to **Project management and accounting** > **Periodic** > **Project operations integration** > **Import beginning balances**.
1. Select **Ok** to generate the beginning balance journal.

> [!NOTE]
> Transactions generated in Project Operations actuals after the **cut-off date** import through the **Import from staging** process and are processed by the **Project Operations integration journal**.

### Beginning balance journal

After you run the **Import beginning balances** process, the system creates a **Beginning balance journal** and its lines. The journal includes all **Project Operations** actual transactions dated on or before the **cut-off date** to establish the opening balances.

To view and post the beginning balance journal, follow these steps.

1. Go to **Project management and accounting** > **Journals** > **Beginning balance**.
1. Select **Lines**.
1. Select **Post** to post the beginning balance journal.

The system generates the **project subledger** immediately after you post the project balance journal.

|Contract line type|Transaction type|Cost status|Accrued revenue|Transaction status|
|--|--|--|--|--|
|Time & Material|Project cost|Profit & loss|Not applicable|Posted|
|Time & Material|Unbilled sales|Not applicable|Default from Project cost and revenue profile rule|Posted|
|Time & Material|Billed sales|Not applicable|Profit and loss|Fully invoiced|
|Fixed price|Project cost|Default from Project cost and revenue profile rule|Not applicable|Posted|
|None (No contract line)|Project cost|Profit and loss|Not applicable|Posted|

> [!NOTE]
> Use Project Operations journals to upload beginning balances. After confirmation, the actuals generate **beginning balance journals** in **Dynamics 365 Finance**.
> 
> Posting the beginning balance journal doesn't generate financial transactions; it only generates the project subledger.
> 
> **Billed Milestones and retainers** aren't supported yet with this feature. Refer [Migrate fully invoiced billing milestones at cutover](../advanced-configuration/migrating-invoiced-milestones.md) to migrate Billed Milestones. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
