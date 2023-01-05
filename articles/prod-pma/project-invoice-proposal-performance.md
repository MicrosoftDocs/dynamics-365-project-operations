---
# required metadata

title: Project invoice proposal performance features
description: This article provides information about performance improvements to project invoice proposals.
author: ryansandness
ms.date: 01/4/2022
ms.topic: article
ms.prod: 
ms.technology: 

# optional metadata

ms.search.form: 
# ROBOTS: 
audience: Application User, IT Pro
# ms.devlang: 
ms.reviewer: johnmichalak

# ms.tgt_pltfrm: 
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
# ms.search.industry: 
ms.author: ryansandness
ms.search.validFrom: 20121-03-05
ms.dyn365.ops.version: 10.0.18

---

# Project invoice proposal performance features

[!include [banner](../includes/banner.md)]

When you create a new invoice proposal, you may encounter slowner processing when the number of projects and transactions increase. This article describes features you can enable to work more efficiently.

## Enable project invoice proposal performance enhancement

This feature improves performance and reduces the time necessary to create an invoice proposal. It enables multi-threaded tasks for the invoice proposal creation and improves the logic used to scan projects for transactions that need invoices.

This feature introduces a parameter in the **Invoice** tab on the **Project Management and accounting parameters** page to **Display available transactions automatically**. This parameter is set to **No** initially to prevent transactions from displaying while they are loading when the **Create invoice proposal** form opens. Instead, transactions display after the search button is used. This encourages users to select criteria to filter transactions they may not need before the query is run, thereby helping to reduce the need to refine and search again. This parameter applies to all users of the legal entity and prevents individual users from changing their settings on the **Create invoice proposal** form. 

To enable the **Project invoice proposal performance enhancement** feature, complete the following steps.

1. Go to **Feature management** > **All**. In the feature list, locate **Project invoice proposal performance enhancement**.
1. Select **Enable now**.
1. Refresh your browser, and then create a new invoice proposal.

By default, the value for **Subtasks** is set to **4** for all legal entities once the feature is enabled. This value can be modified within the **Project management and accounting parameters** page under the **Invoicing** tab for the parameter of **Number of subtasks for invoice proposal creation in batch**.

> [!NOTE]
> The **Project invoice proposal performance** feature does not address invoicing when billing rules are used.
>
> Regardless of the value you have entered for **Subtasks**, when the batch process runs to create invoice proposals, subtasks will split the tasks to a maximum number that is based on the number of contracts with invoiceable transactions. For example, if you enter **3** for the number of subtasks for invoice proposal creation in batch, and there are only two contracts with invoiceable transactions, only two subtasks are created. 

## Enable performance improvement to filter by project for project invoice proposals with billing rules

This feature improves performance during invoice proposal creation when using time and material or milestone billing rules with many billing rules and a high volume of transactions and milestones.

When there are manu milestones or project transactions, users can experience issues interacting with the invoice proposal from billing rule form. In some cases, the form can get stuck loading or stop responding when interacting with the form.

Performance is improved by enforcing the **Project** filter to return transactions that only match the filter. Previously, if the project filter was set to a **Subproject** or **Parent project** and the billing rules were assigned to anything in the parent, then sibling projects, or child projects would be returned. Users can now filter to specific subprojects, the parent project, or leave the **Project** filter blank to return all transactions for the specified contract.

If you create an invoice proposal from within a project, the **Project** filter will be read-only and locked to the current parent or subproject. You can create an invoice proposal from the contract, or from the **Project invoice proposals** menu if you want to add or change the **Project** filter that is specified.

> [!NOTE]
> The project filter only works for time and material, or milestone type billing rules because only these billing rule types specify the project as part of the configuration.

To enable the **Performance improvement to filter by project for project invoice proposals with billing rules** feature, complete the following steps.

1. Go to **Feature management** > **All**. In the feature list, locate **Performance improvement to filter by project for project invoice proposals with billing rules**.
1. Select **Enable now**.
1. Refresh your browser, and then create a new invoice proposal.

This feature can be used with the **Project invoice proposal performance enhancement** feature to prevent the automatic display of transactions prior to applying filters.
