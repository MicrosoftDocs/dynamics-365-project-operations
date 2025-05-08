---
title: Project invoice proposal performance features
description: This article provides information about performance improvements to project invoice proposals.
author: ryansandness
ms.date: 06/04/2024
ms.topic: how-to
ms.custom: 
  - bap-template
audience: Application User, IT Pro
ms.reviewer: johnmichalak
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: ryansandness
ms.search.validFrom: 20121-03-05
ms.dyn365.ops.version: 10.0.18

---

# Project invoice proposal performance features

[!include [banner](../includes/banner.md)]

When you create, edit, or post an invoice proposal, you might encounter slower processing when the number of projects and transactions increases. This article describes features that you can enable to help yourself work more efficiently.

## Features to enhance the performance of project invoice proposal creation

### Project invoice proposal performance enhancement

This feature helps improve performance and reduce the time required to create an invoice proposal. It enables multithreaded tasks for invoice proposal creation and improves the logic used to scan projects for transactions that need invoices.

This feature introduces a **Display available transactions automatically** option on the **Invoice** tab of the **Project Management and accounting parameters** page. By default, the option is set to **No**. This setting prevents transactions from appearing while they're being loaded when the **Create invoice proposal** page is opened. Instead, transactions appear only after the search button is used. This behavior encourages users to select criteria to filter out transactions that they don't require before the query runs, to help reduce the need to refine and search again. The option applies to all users of the legal entity and prevents individual users from changing their settings on the **Create invoice proposal** page.

To enable the **Project invoice proposal performance enhancement** feature, follow these steps.

1. Open the **Feature management** workspace, and select the **All** tab.
1. In the feature list, find **Project invoice proposal performance enhancement**.
1. Select **Enable now**.
1. Refresh your browser, and then create a new invoice proposal.

Project invoice proposals that are created in batch mode are created more quickly if you split the work that must be done into multiple subtasks. By default, the number of subtasks is set to **4** for all legal entities after the feature is enabled. You can change this number by using the **Number of subtasks for invoice proposal creation in batch** field on the **Invoicing** tab of the **Project management and accounting parameters** page.

> [!NOTE]
> The **Project invoice proposal performance** feature doesn't apply to invoicing when billing rules are used.
>
> The transactions for an individual contract won't be split into multiple subtasks. If only one or two contracts have transactions to invoice, the number of subtasks configured won't be used. Instead, a subtask is created for each contract. For example, if you enter **3** as the number of subtasks for invoice proposal creation in batch mode, and only two contracts have invoiceable transactions, only two subtasks are created.

### Performance improvement to filter by project for project invoice proposals with billing rules

This feature helps improve performance during invoice proposal creation when you use time-and-material or milestone billing rules that have many billing rules and a high volume of transactions and milestones.

If there are many milestones or project transactions, users can experience issues when they interact with the invoice proposal from the billing rule page. In some cases, the page can get stuck while it's being loaded, or it can stop responding when users interact with it.

To help improve performance, this feature enforces the **Project** filter, so that only transactions that match the filter are returned. Previously, if the **Project** filter was set to a subproject or a parent project, and the billing rules were assigned to anything in the parent project, sibling projects or child projects were returned. Users can now filter to specific subprojects or the parent project. Alternatively, they can leave the **Project** filter blank to return all transactions for the specified contract.

If you create an invoice proposal from within a project, the **Project** filter is read-only and locked to the current parent project or subproject. If you want to add or change the **Project** filter specified, you can create an invoice proposal from the contract or the **Project invoice proposals** menu.

> [!NOTE]
> The **Project** filter works only for time-and-material and milestone billing rules, because only these types of billing rules specify the project as part of the configuration.

To enable the **Performance improvement to filter by project for project invoice proposals with billing rules** feature, follow these steps.

1. Open the **Feature management** workspace, and select the **All** tab.
1. In the feature list, find **Performance improvement to filter by project for project invoice proposals with billing rules**.
1. Select **Enable now**.
1. Refresh your browser, and then create a new invoice proposal.

This feature can be used together with the **Project invoice proposal performance enhancement** feature to prevent the automatic display of transactions before filters are applied.

### Enable project invoice proposal creation specific to selected project

This feature helps improve performance during invoice proposal creation when you don't use billing rules and have a high volume of transactions split across subprojects.

To help improve performance, this feature enforces the **Project** filter to filter from the starting project, so that only transactions that match the filter are returned. Previously, if the **Project** filter was set to a subproject, the filter on the transaction selection page went up one level by default, to the parent project level. Users can now filter to specific subprojects or the parent project.

If you create an invoice proposal in the context of a subproject, the **Project** filter is editable and is set to the current parent project or subproject.

## Features to enhance editing of project invoice proposals

### Disable automatic refresh of summaries

If you often work with large invoices where edits are required to add and remove transactions, you might benefit from delaying summary calculations until you're ready. Instead of recalculating the tax and proposal totals after each change, you can make several changes and then update the summary data once at the end.

The **Disable automatic refresh of summaries** feature is an optional parameter that you enable on the **Invoice** tab of the **Project management and accounting parameters** page. The **Use Project invoice proposal and invoice journal forms with the Header and Lines view** feature is required as a prerequisite to make the parameter available.

When the feature is enabled, the following changes can be observed:

- On the **Project invoice proposals** page, a new **Recalculates totals status** column is added. The possible values are **required** and **not required**.
- If the parameter isn't enabled, the value of the **Invoice amount** field on the same page isn't updated until recalculation occurs.
- On **Invoice proposals** page, a **Refresh** button is available but is disabled by default.
- When a transaction is edited, added, or removed, the values on the **Invoice proposals transaction summaries** FastTab don't reflect the new values.
- Users can select the **Refresh** button to refresh interactively or in batch mode.
- Users can also post instead of refreshing. The refresh then occurs automatically.
