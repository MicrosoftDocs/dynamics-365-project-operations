---
# required metadata

title: Configure and use project funding limits
description: This article explains how to configure and use project funding limits,
author: ryansandness
ms.date: 11/2/2023
ms.topic: conceptual
ms.custom: bap-template

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak

# ms.search.industry: 
ms.author: ryansandness
ms.search.validFrom: 2023-11-1
ms.dyn365.ops.version: AX 10.0.36

---

# Configure and use project funding limits

_**Applies To:** Project Operations for stocked/production based scenarios_

[!include[banner](../includes/banner.md)]

This article explains how to configure and use project funding limits.

Use funding limits to limit the amount billed on a project invoice. You might have a grant or a contractual agreement for goods or services that can't exceed a specified amount. You can configure and enforce these limits using the **Project contract** configuration and setup.

Funding limits are often used with other features such as **funding sources** and **funding rules**. For more information these concepts, see,[project contracts](./project-contracts.md).

When you establish funding limits on a project contract, you can navigate to the project contract and review the **Funding limits** tab. This tab shows you the **Funding limit** amount that represents the maximum amount to invoice. The **Committed amount** represents the amount used but hasn't reached its final state. The **Spent amount** is the amount invoiced or has moved past the committed state.

## Enable recalculation of funding limits

In the 10.0.37 release, new functionality is available to help with self-healing scenarios for configuration mistakes, product defects, and customization issues. This feature allows monitoring and updating funding limits that weren't correctly calculated in the category of **Spent amount** during document processing. You can **Enable recalculation of funding limits** from the **Project management and accounting parameters** form on the **Invoice** tab.

After you **Enable recalculation of funding limits**, two new forms are made available on **Project management and accounting** > **Periodic** > **Funding Limits**.

### Recalculate spending limits

The **Recalculate spending limits** form evaluates one or more funding limits to check for any inconsistencies and optionally lets the you save the recalculated value back to the **Funding limit** **Spent amount**.

To recalculate the **Spent amount** without updating values, set **Update spent amounts** to **No**. You can then set a filter for **project contract ID** or set a filter for one or more contracts. This process populates a new list of data that contains a list of the **Project contracts** and associated **Funding limits**. The process also indicates if a variance was found as part of the recalculation.

Optionally, the batch process can be scheduled so contracts can be automatically scanned on weekly basis or some other interval.

To recalculate spent amounts with updating values, set **Update spent amounts** to **yes**. A filter is required, and you receive the following error message filter criteria isn't specified.

``` console
Filter criteria are required for updating amounts. Provide a value or range and try again.
```

A filter can be provided for one contract, a list, or a range of contracts when an update is performed. For more information about filtering, see [Advanced filtering and query syntax](/dynamics365/fin-ops-core/fin-ops/get-started/advanced-filtering-query-options).

### View funding limit history

The **Funding limit history** form contains a list of all contracts where the **Recalculate spent amounts** process runs. If contracts exist but aren’t included in a recalculate job execution, they aren't on the list.

Note: By default, the form opens to a list of a contract where the spent amount doesn’t match the calculated spent amount. If no **funding limits** are found to be out of sync, then the list is blank. Clear the **Requires update filter** on the left to see the **Project contracts** and their **Funding limit history**.

> [!NOTE]
> The **Requires update** filter looks to the most recent recalculation record for evaluation purposes.

On the right is the history for the selected **project contract**. Two important fields to note are **Update required** and **Updated**.

- **Update required** means that the **Actual spent**, which is the amount on the **Funding limit** doesn't match the **Calculated spent**, which is the amount determined from the **Recalculate spent amount** process.
- **Updated** indicates a **Recalculate spent amount** process ran, recalculated the **Spent amount** again, and updated the **Funding limit** with the new amount.
  
The **Funding limit history** grid introduces a new field named **Line number** that corresponds to the line number on the funding limit within the project contract.

You can personalize this grid to add more details to help you determine which funding limit is being displayed without having a second tab open for the project contract.

If you need to update the **spent amount**, you can select the project contract and click **Update spent** in the ribbon for this project contract. The **Recalculate spent amount** process runs immediately and performs an update.

The **Funding limit spent amount history** data entity is available from with **Data Management** or from the **Microsoft Excel** icon within **Funding limit history**. An export from **Data Management** gives the complete history, while the export to **Microsoft Excel** exports results for the selected contract.
