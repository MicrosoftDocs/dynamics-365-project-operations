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

# Managed beginning balances for Project Operations integrated with ERP deployments

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations integrated with ERP deployments._

**Beginning balances**, also referred to as **opening balances**, represent transactions that were incurred outside of **Dynamics 365 Project operations** before the project was set up in the system. These balances typically arise during scenarios such as:

* System migration from a legacy ERP
* When the customer previously maintained financial records using other tools or manual processes

When transitioning to **Dynamics 365 Project Operations**, it’s essential to bring forward opening balances for projects, customers, and related financial data to ensure continuity and accurate reporting. 
This process involves setting up initial values for costs, revenue, WIP (Work in Progress), and billing.

This article provides an overview to manage or upload the Project opening balances in Microsoft Dynamics 365 Project Operations. This feature is seamlessly integrated with Dynamics 365 Finance. 

## Prerequisites
### Features

To use the functionality, activate the following features:
- **Enable beginning balances in Project Operations Integrated with ERP** in Dynamics 365 Finance

### Minimum versions required

To use the feature for Project Operations integrated deployments, you must have the following versions:
- **Dynamics 365 Finance** version 10.0.46 or later

## Import beginning balances
New customers implementing Project Operations have a need to enter beginning balances for projects that are in process. For the integrated Project Operations scenario, the system can generate beginning balance amounts based on actuals as of a **specified date**. 
This date would be considered a **cut-off date** and assume that the **General ledger** has been already updated. 
This is very important to make sure that the **fixed price revenue recognition** process can be correctly calculated. 
Once the balances are integrated and posted, the recommendation would be that the **revenue recognition** process would be run for beginning balances. 

### Project management and accounting parameters
To create **beginning balances** as of a **specified date**, follow below steps:

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
2. In the **General** tab, Select **Create beginning balances**.
3. In the **As of date**, Enter the **cut of date**.
4. Select the beginning balance journal name.

> [!NOTE]
> The **Cut-off date** field becomes **non-editable** after the first transaction is posted using the **Beginning Balance journal**.
> 
### Import beginning balances

When **Actuals** are imported into **Dynamics 365 Finance** from **Dynamics 365 Project operations** with on or before the specified **As of date**, the system creates **Beginning Balance journal** lines instead of project operations **integration journal** lines.

Beginning Balance journals do not generate any accounting entries in the general ledger and only update the project subledger for tracking purposes.

To generate the beginning balances in **Dynamics 365 Finance**. follow below steps:
1. Go to **Project management and accounting** > **Periodic** > **Project operations integration** > **Import beginning balances**.
2. Click **Ok** to generate beginning balance journal.

> [!NOTE]
> Any transaction generated in Project Operations actuals after the **cut-off date** is imported through the **Import from staging** process and processed using the **Project Operations integration journal**.
> 
### Beginning balance journal
After running the **Import beginning balances** process, the system creates a **Beginning balance journal** along with its journal lines.
All actual transactions in **Project Operations** that have a transaction date on or before the defined **cut-off date** are included in this journal to establish the opening balances.

To **view** and **post** the beginning balance journal, follow below steps:
1. Go to **Project management and accounting** > **Journals** > **Beginning balance**.
2. Clck on **Lines**.
3. Click **Post** to post the project beginning balance journal.

The system generates the **project subledger** immediately after posting the project balance journal, as shown below:

|Contract line|Project transaction|Project transaction posting|
|--|--|--|
|Time & Material|Project cost|Profit and loss|
|Time & Material|Unbilled sales|Project cost and revenue profile rule|
|Time & Material|Billed sales|Profit and loss|
|Fixed price|Project cost|Project cost and revenue profile rule|
|None|Project cost|Profit and loss|

> [!NOTE]
> Project operations journals is the best option to upload the beginning balances and actual are generated once the journals are confirmed. These actuals are used to generate **beginning balance journals** in **Dynamics 365 Finance**.
> 
> Beginning balance journal posting process **does not generate financial transactions** and generates project subledger only.
> 
> **Billed Milestones and retainers** are currently not supported with this process and will be added as part of future releases. 
