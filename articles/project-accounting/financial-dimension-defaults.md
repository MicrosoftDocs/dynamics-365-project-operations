---
title: Financial dimension defaults
description: This article provides information about how to set up financial dimension defaults.
author: sigitac
ms.date: 12/14/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Financial dimension defaults

_**Applies To:** Project Operations for resource/non-stocked based scenarios_



Dynamics 365 Project Operations uses the [Financial dimensions](/dynamics365/finance/general-ledger/financial-dimensions) framework in Dynamics 365 Finance to provide additional insights on project subledger and general ledger transactions.

Default financial dimensions can be set on a customer, project funding source, milestone, project contract line, or project.

## Define default financial dimensions for a customer

Customer dimension defaults are specified in Finance. Complete the following steps to set dimension defaults.

1. Go to **Accounts receivable** > **Customers** > **All customers**.
2. On the **Customers** page, on the **Financial dimensions** tab, set the financial dimension values for specific customer.

## Define default financial dimensions for project contracts

Project contracts are created and maintained in Common Data Service (CDS). Accounting attributes for project contracts are set in the **Project management and accounting** module in Finance.

### Set financial dimensions for a project funding source

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
2. Select the record you want to update, and on the **Project contract** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Funding sources** tab.
4. Set the financial dimension defaults. Notice that the financial dimensions default from the customer account.

### Set financial dimensions for a project contract line

1. Go to **Project management and accounting** > **Projects** > **Project contracts**.
2. Select the record you want to update and on the **Project contract** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Contract lines** tab.
4. Set the financial dimension defaults. The financial dimension defaults are applicable and can be used only with Fixed price (milestone) contract lines.

These defaults are used on related project on-account transactions and invoice lines.

## Define default financial dimensions for projects

Projects are created and maintained in CDS. Accounting attributes for projects are set in the **Project management and accounting** module in Finance.

1. Go to **Project management and accounting** > **Projects** > **All projects**.
2. Select the record that you want to update and on the **Project** tab, select **Show default accounting**.
3. Expand **Related information** and select the **Setup** tab.
4. Set the financial dimension defaults. Notice that financial dimensions default from the customer account. If the project is associated with a contract line with multiple project contract customers, the primary customer is used to default financial dimensions.

Project default financial dimensions are used to set journal line defaults for time, expense, and fee transactions in the **Project Operations Integration Journal** and on related project invoice lines.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
