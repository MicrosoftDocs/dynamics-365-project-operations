---
# required metadata

title: Project funding limits
description: This article explains how to configure and use project funding limits
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

# Project funding limits

_**Applies To:** Project Operations for stocked/production based scenarios_

[!include[banner](../includes/banner.md)]

**Funding limits** are used to limit the amount that can be billed on a project invoice. Often customers may have a grant or a contractual agreement for goods or services to not exceed a certain amount. The configuration and setup on the **Project contract** are how you can configure and enforce these limits.

**Funding limits** are often used with other features such as **funding sources** and **funding rules**. Review these concepts in [project contracts](./project-contracts.md) for additional details.

After you have established the **funding limits** on the **project contract**, you can navigate to the project contract and review the **Funding limits** tab. This tab will show you the **funding limit** amount which represents the maximum amount to invoice, the **committed amount** representing amounts that will be used, but have not yet reached their final state, and the **spent amount**, which is the amount that has been invoiced or moved past the committed state.

## Enable recalculation of funding limits

In the 10.0.37 release, new functionality is available to help with self-healing scenarios for configuration mistakes, product defects, and customization issues. This feature allows monitoring and updating **funding limits** that were not correctly calculated in the category of **spent amount** during document processing. This feature can be enabled from the **Project management and accounting parameters** form on the **invoice** tab. There is a setting under **project contract** for **enable recalculation of funding limits**.

After enabling this parameter and two new forms will be made available under **Project management and accounting** > **Periodic** > **Funding Limits**.

### Recalculate spending limits

The first new form is **Recalculate spending limits**, which is a process to evaluate one or more **funding limits** to check for any inconsistencies, and optionally lets the user to save the recalculated value back to the **funding limit** **spent amount**.
To recalculate **spent amounts** without updating values, you leave the parameter for **update spent amounts** to **no**. You can then set a filter for **project contract ID** or set a filter for one or more contracts. This process will populate a new list of data which contains a list of the **project contracts** and associated **funding limits**. It will also indicate if a variance was found as part of the recalculation.
Optionally, the batch process can be scheduled so that contracts can be automatically scanned on weekly basis or some other regular interval.
To recalculate spent amounts with updating values, you leave the parameter for **update spent amounts** to **yes**. A filter is required, and you will receive the below error message if no filter criteria is specified.

<i>Filter criteria is required for updating amounts. Provide a value or range and try again.</i>

A filter can be provided for a single contract, a list, or a range of contracts when an update is performed. For more information about filtering, see [Advanced filtering and query syntax](/dynamics365/fin-ops-core/fin-ops/get-started/advanced-filtering-query-options).

### Funding limit history

The **Funding limit history** form contains a list on the left of all contracts where the **Recalculate spent amounts** process has run. If contracts exist but the contract wasn’t included in a recalculate job execution, it won’t be in the list.

Note: By default, the form opens to a list of a contract where the spent amount doesn’t match the calculated spent amount. If no **funding limits** are found to be out of sync, then the list will be blank. Clear the **Requires update filter** on the left to see the **project contracts** and their **funding limit history**.

Note: The **Requires update** filter looks to the most recent recalculation record for evaluation purposes.

On the right, you will see the history for the selected **project contract**.
Two important fields to note are **Update required** and **Updated**.
**Update required** means that the **Actual spent**, which is the amount on the **funding limit** does not match the **Calculated spent**, which is the amount determined from the **Recalculate spent amount** process.
**Updated** indicates a **Recalculate spent amount** process ran, re-calculated the **spent amount** again, and updated the **funding limit** with the new amount.
The **Funding limit history** grid introduces a new field named **line number** which corresponds to the line number on the funding limit within the **project contract**.

You can personalize this grid as well to add additional details to help you determine which funding limit is being displayed without having a second tab open for the project contract.

If you need to update the **spent amount**, you can select the project contract and click **Update spent** in the ribbon for this **project contract**. The **Recalculate spent amount** process will run immediately and perform an update.

The **Funding limit spent amount history** data entity is available from with **Data Management** or from the **Microsoft Excel** icon within **Funding limit history**. An export from **Data Management** will give the complete history, while the export to **Excel** will export results for the selected contract.
