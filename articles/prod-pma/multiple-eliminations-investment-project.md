---
title: Enable Handling of Multiple Eliminations in Investment Projects
description: Learn how to enable and use the multiple eliminations feature for investment projects in Dynamics 365 Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 05/30/2026
ms.reviewer: johnmichalak
ms.topic: how-to
ms.custom: 
  - bap-template

---
 
# Enable multiple eliminations for an investment project

[!INCLUDE[banner](../includes/banner.md)]

**Applies to:** Dynamics 365 Project Operations for Integrated with ERP, Dynamics 365 Project Operations for manufacturing

## Overview

In Dynamics 365 Project Operations, **investment projects** track costs that you capitalize rather than expense immediately. *Elimination* is the accounting process that reverses or removes capitalized costs from an investment project, transferring value to the associated fixed asset or ledger account.

By default, only a **single** elimination transaction is permitted per investment project. The **Enable Handling of Multiple Eliminations in Investment Projects** feature removes this restriction, so finance and project accountants can **post multiple elimination transactions** against a single investment **project—supporting** staged capitalization, cost overruns, and partial expense scenarios.

## Key business scenarios

| Scenario | How this feature helps |
|---|---|
| **Staged asset capitalization** | Eliminate costs phase-by-phase as each wing or section is placed in service |
| **Cost overruns and scope changes** | Post a second elimination for incremental approved costs without reversing the original |
| **Partial capitalization** | Eliminate only qualifying cost components; leave ineligible costs for expense recognition |
| **Audit and compliance** | Single project number with per-voucher audit trail supports reconciliation |

> [!IMPORTANT]
> This feature changes elimination posting behavior. Review your organization's capitalization policy before enabling it in production.

## Prerequisites

Before you can enable multiple eliminations for an investment project, ensure you meet the following prerequisites:

- Use **Dynamics 365 Finance version 10.0.49.**
- In Feature management, enable the **Enable Handling of Multiple Eliminations in Investment Projects** feature.

## Project management and accounting parameters

To update the Project management and accounting parameters, follow these steps:

1. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1. Go to the **Revenue recognition** tab.
1. **Allow multiple elimination accounts** - This option allows you to use multiple accounts for elimination purposes. If you don't need multiple elimination accounts and prefer to use the account configured for revenue recognition, turn off this option.
1. **Allow transaction selection** - This option allows you to add or remove transactions in the elimination proposal form. If you enable this option, you can't modify the transactions on the form. All defaulted transactions are used for elimination.
1. Go to the **Number sequence** tab.
1. Configure number sequence for **elimination proposal**.

## Perform multiple eliminations

To perform the elimination process, generate an elimination proposal by following these steps:

1. Go to **Project management and accounting > Projects > All projects** and open your investment project.
1. Go to the **Manage** action pane, and select **Revenue recognition**.
1. Generate **Revenue recognition** for the period, and select **Post**.
1. Go to **Project management and accounting > Investment Projects > Elimination Proposal** or **Revenue recognition > Elimination Proposal**.
1. Select **+ New** to create the elimination proposal.
1. Select the **Revenue recognition project**, **elimination date**, and select **OK**.
1. In the **Transactions** tab, view the list of **transactions** available for the elimination process. Consider all transactions that aren't yet eliminated but undergo revenue recognition.
1. Use the **Add** or **Delete** button to add or remove transactions from the elimination proposal.
1. In the **Elimination accounts** tab, enter the ledger account, fixed asset, or other project, and distribute the total amount to the selected accounts.
1. Select **Post** to post the **elimination proposal**.

### Repeat as needed

Repeat steps 1–9 for each subsequent capitalization stage. Each transaction gets its own voucher and audit trail.

### Eliminate the project (optional)

Once you eliminate all costs, select the **Eliminate** option while posting the elimination proposal. The following validations are performed during the posting process when you select the **Eliminate** option:

1. All cost transactions must be fully eliminated.
1. Revenue recognition must be completed and posted.
1. No pending elimination transactions.
  
## Reverse eliminations

Use **reverse elimination** to **undo** previously posted elimination entries when changes occur after the elimination process.

To reverse the elimination proposal, follow these steps:

1. Go to **Project management and accounting > Investment projects > Elimination proposal**.
1. Select the elimination proposal with **posted** status.
1. Select **Reverse** to reverse the elimination proposal. You can use all transactions reversed through this process in future elimination cycles.

> [!NOTE]
> **Don't disable** this feature after use in production. It restricts future eliminations on already affected projects.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
