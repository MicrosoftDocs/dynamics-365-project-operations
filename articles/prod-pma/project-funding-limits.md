---
title: Configure and use project funding limits
description: Learn how to configure and enforce project funding limits to control billing on invoices. Discover setup tips and recalculation features for accurate tracking.
author: ryansandness
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: bap-template
audience: Application User
ms.reviewer: johnmichalak
ms.author: ryansandness
ms.search.validFrom: 2023-11-1
ms.dyn365.ops.version: AX 10.0.36

---

# Configure and use project funding limits

[!include[banner](../includes/banner.md)]

_**Applies To:** Project Operations for manufacturing based scenarios_

This article explains how to configure and use project funding limits.

Use funding limits to limit the amount that you bill on a project invoice. For example, you might have a grant or a contractual agreement for goods or services that can't exceed a specified amount. You can configure and enforce these limits by using the **Project contract** configuration and setup.

Funding limits are often used together with other features, such as funding sources and funding rules. For more information about these concepts, see [Project contracts](./project-contracts.md).

When you establish funding limits on a project contract, you can go to the project contract and review the **Funding limits** tab. On this tab, the value of the **Funding limit** field represents the maximum amount to invoice. The value of the **Committed amount** represents the amount that you used but that didn't reach its final state. The value in the **Spent amount** field represents the amount that you invoiced or that moved past the committed state.

## Enable recalculation of funding limits

In the 10.0.37 release, new functionality is available to help with self-healing scenarios for configuration mistakes, product defects, and customization problems. The feature lets you monitor and update funding limits that weren't correctly calculated in the **Spent amount** category during document processing. You can enable the **Enable recalculation of funding limits** feature on the **Invoice** tab of the **Project management and accounting parameters** page.

After you enable the **Enable recalculation of funding limits** feature, two new pages become available at **Project management and accounting** \> **Periodic** \> **Funding Limits**: **Recalculate spending limits** and **Funding limit history**.

### Recalculate spending limits

The **Recalculate spending limits** page evaluates one or more funding limits to check for inconsistencies. You can optionally save the recalculated value back to the **Spent amount** field for the funding limit.

To recalculate spent amounts without updating values, set the **Update spent amounts** option to **No**. You can then set a filter for a project contract ID, or for one or more contracts. The recalculation process populates a new list of data that shows the project contracts and associated funding limits. The process also indicates whether a variance was found as part of the recalculation.

You can optionally schedule the batch process so that contracts are automatically scanned on a weekly basis or at some other interval.

To recalculate spent amounts and update values, set the **Update spent amounts** option to **Yes**. A filter is required. If you don't specify filter criteria, you receive the following error message:

> Filter criteria are required for updating amounts. Provide a value or range and try again.

You can provide a filter for one contract, a list of contracts, or a range of contracts when an update is performed. For more information about filtering, see [Advanced filtering and query syntax](/dynamics365/fin-ops-core/fin-ops/get-started/advanced-filtering-query-options).

### Funding limit history

The **Funding limit history** page contains a list of all contracts where the **Recalculate spent amounts** process runs. If any contracts aren't included in a recalculate job execution, they don't appear in the list.

> [!NOTE]
> By default, when you open the **Funding limit history** page, it shows a list of contracts where the spent amount doesn't match the calculated spent amount. If no funding limits are out of sync, the list is blank. Clear the **Requires update** filter to view the project contracts and their funding limit history.
>
> The **Requires update** filter looks at the most recent recalculation record for evaluation purposes.

On the right, you see the history for the selected project contract. Two important fields to note are **Update required** and **Updated**.

- **Update required** indicates that the **Actual spent** value, which is the amount of the funding limit, doesn't match the **Calculated spent** value, which is the amount that the **Recalculate spent amount** process determines.
- **Updated** indicates that a **Recalculate spent amount** process ran, recalculated the **Spent amount** value, and updated the funding limit with the new amount.

The grid on the **Funding limit history** page includes a new field named **Line number**. The value of this field corresponds to the line number of the funding limit in the project contract.

You can personalize the grid and add more details. In this way, you can more easily determine which funding limit is being shown without having to open a second tab for the project contract.

If you must update the spent amount, you can select the project contract and then select **Update spent** on the Action Pane for that project contract. The **Recalculate spent amount** process immediately runs and performs an update.

You can access the **Funding limit spent amount history** data entity from Data Management or from the **Microsoft Excel** button on the **Funding limit history** page. An export from Data Management gives the complete history, whereas an export to Excel exports results only for the selected contract.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
