---
# required metadata

title: Project invoice proposal performance
description: This article provides information about performance improvements to project invoice proposals.
author: Yowelle
ms.date: 01/3/2022
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

When you create a new invoice proposal you might encounter some slowness in processing as the number of projects and transactions increase. Read on to learn about features that can be enabled to work more efficiently.

## Enable project invoice proposal performance enhancement

This feature improves performance and reduces the time necessary to create an invoice proposal. It enables multi-threaded tasks for the invoice proposal creation and improves the logic on how projects are scanned for transactions to be invoiced.

This feature also introduces a new parameter in the **Invoice** tab of the **Project Management and accounting parameters** page to **Display available transactions automatically**. This parameter is set to **No** initially, which will prevent the display of transactions loading upon initial opening of the invoice proposal form until the search button is used. This setting applies to all users of the legal entity and prevents individual users from changing their settings on the **Create invoice proposal** form. It is recommended to set this parameter to **No** to allow users to select and enter filters first rather than searching for transactions that may not be applicable before refining and searching again.

To enable the **Project invoice proposal performance enhancement** feature to reduce the time needed to create a new invoice proposal for posted project transactions, complete the following steps.

1. Go to **Feature management** > **All**. In the feature list, locate **Project invoice proposal performance enhancement**.
2. Select **Enable now**.
3. Refresh your browser, and then create a new invoice proposal.

A default value of four subtasks will default for all legal entities once the feature is enabled. This value can be modified within the **Project management and accounting parameters** page under the **Invoicing** tab for the parameter of **Number of subtasks for invoice proposal creation in batch**.

> [!NOTE]
> The Project invoice proposal performance feature does not address invoicing when billing rules are used.
>
> During the batch process to create invoice proposals, the number of subtasks will split the tasks to a maximum number based on the number of contracts with invoiceable transactions, regardless of what you have entered. For example, if you enter **3** for the number of subtasks for invoice proposal creation in batch, and there are only two contracts with invoiceable transactions, only two subtasks are created.

## Enable performance improvement to filter by project for project invoice proposals with billing rules

This feature improves performance during invoice proposal creation when using time and material or milestone billing rules with many billing rules and a high volume of transactions and milestones.

With a large number of milestones or project transactions, users could experience issues interacting with the invoice proposal from billing rule form. In some cases the form could get stuck loading or stop responding when interacting with the form.

This feature improves performance by enforcing the **Project** filter to return transactions only matching the filter. Previously, if the project filter was set to a subproject or parent project then billing rules assigned to anything in the parent, sibling projects, or child projects would be returned. Users can now filter to specific subprojects, the parent project, or leave the **Project** filter blank to return all transactions for the specified contract.

> [!NOTE]
> The project filter only works for time and material or milestone type billing rules as only these billing rule types specify the project as part of the configuration.

To enable the **performance improvement to filter by project for project invoice proposals with billing rules** feature to reduce the time needed to create a new invoice proposal for posted project transactions, complete the following steps.

1. Go to **Feature management** > **All**. In the feature list, locate **performance improvement to filter by project for project invoice proposals with billing rules**.
2. Select **Enable now**.
3. Refresh your browser, and then create a new invoice proposal.

This feature can be used with the project invoice proposal performance enhancement feature to prevent the automatic display of transactions prior to applying filters.
