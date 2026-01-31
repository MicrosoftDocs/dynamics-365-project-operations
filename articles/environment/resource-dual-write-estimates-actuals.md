---
title: Project estimates and actuals integration
description: This article provides information about Project Operations dual-write integration for project estimates and actuals.
author: suvaidya
ms.author: nshrivastava
ms.date: 01/23/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project estimates and actuals integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article provides information about Project Operations dual-write integration for project estimates and actuals.

## Project estimates

Create and maintain project labor, expense, and material estimates in Microsoft Dataverse. These estimates synchronize to finance and operations apps for accounting purposes. You can't create, update, or delete estimates through the finance and operations apps.

Creating estimates requires a valid accounting configuration for the project. Projects that are associated with contract lines must have a valid project cost and revenue profile defined in the Project cost and revenue profile rules. For more information, see [Configure accounting for billable projects](../project-accounting/configure-accounting-billable-projects.md#configure-project-cost-and-revenue-profile-rules).

## Labor estimates

The project manager or Resource Manager creates labor estimates and assigns a generic or named resource to the project task. You can review resource assignment records on the **Resource Assignments** tab on the **Project Details** page in Dataverse. Resource assignment records in Dataverse create hour forecast records in finance and operations apps by using **Project Operations integration entity for hour estimates (msdyn\_resourceassignments)**.

:::image type="content" source="./Media/DW4LaborEstimates.png" alt-text="Screenshot of labor estimates integration flow between Dataverse and finance and operations apps.":::

Dual-write synchronizes resource assignment records to the staging table (**ProjCDSEstimateHoursImport**), and then uses business logic to create and update hour forecast records (**ProjForecastEmpl**).

The project accountant reviews forecast hour records created in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Hour forecasts**.

## Expense estimates

The project manager creates expense estimates on the **Expense Estimates** tab of the **Project Details** page in Dataverse. Dataverse stores expense estimate records in the **Estimate Line** entity. These estimate records use the transaction class **Expense** and synchronize to expense forecast records in finance and operations apps by using the **Project Operations integration entity for expense estimates (msdyn_estimatelines)**.

:::image type="content" source="./Media/DW4ExpenseEstimates.png" alt-text="Screenshot of expense estimates integration flow between Dataverse and finance and operations apps.":::

Dual-write synchronizes expense estimate records to the staging table **ProjCDSEstimateExpenseImport**. Then, it uses business logic to create and update expense forecast records (**ProjForecastCost**). Estimate lines store sales estimate and cost estimate records separately. The business logic in finance and operations apps populates a single Expense forecast record by using this detail in the staging table.

The project accountant can review expense forecast records in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Expense forecasts**.

## Material estimates

The project manager creates material estimates on the **Material Estimates** tab of the **Project Details** page in Dataverse. Dataverse stores material estimate records in the **Estimate Line** entity. These estimate records use the transaction class **Material** and synchronize to item forecast records in finance and operations apps by using the **Project integration table for material estimates (msdyn_estimatelines)**.

:::image type="content" source="./Media/DW4MaterialEstimates.png" alt-text="Screenshot of material estimates integration flow between Dataverse and finance and operations apps.":::

Dual-write synchronizes material estimate records to the staging table **ProjForecastSalesImpor**. Then, it uses business logic to create and update item forecast records (**ForecastSales**). Estimate lines store sales estimate and cost estimate records separately. The business logic in finance and operations apps populates a single Item forecast record by using this detail in the staging table.

The project accountant can review item forecast records in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Item forecasts**.

## Project actuals

Dataverse creates project actuals based on time, expense, material, and billing activity. This Dataverse entity captures all operational attributes of these transactions, including quantity, cost price, sales price, and project. For more information, see [Actuals](../actuals/actuals-overview.md). The dual-write table map **Project Operations integration actuals (msdyn\_actuals)** synchronizes actual records to finance and operations apps for downstream accounting.

:::image type="content" source="./Media/DW4Actuals.png" alt-text="Screenshot of actuals integration flow between Dataverse and finance and operations apps.":::

The **Project Operations integration actuals** table map synchronizes all the records from the **Actuals** entity in Dataverse, with the attribute **Skip Sync (internal use only)** set to **False**. Dataverse automatically sets this attribute value when you create the record. Set this attribute to **True** in the following examples:

  - Project cost actuals for intercompany transactions. For more information, see [Create intercompany transactions](../project-accounting/create-intercompany-transactions.md). The system skips these records because it recreates the project cost actual in finance and operations apps when you post the intercompany vendor invoice.
  - Negative unbilled sales records created when the proforma invoice is confirmed. The system skips these records because the project subledger in finance and operations apps doesn't reverse the unbilled sales record at invoicing but changes the status to fully invoiced.

The dual-write table map synchronizes the actuals records to the staging table, **ProjCDSActualsImport**. The periodic process **Import from staging table** processes these records when creating Project Operations integration journal lines and project invoice proposal lines. For more information, see [Integration journal in Project Operations](../project-accounting/project-operations-integration-journal.md).

Dataverse also captures the links between the project actual transactions in the **Transaction connection** entity. For more information, see [Link actuals to original records](../actuals/linkingactuals.md). The dual-write table map, **Integration entity for project transaction relationships (msdyn\_transactionconnections)**, synchronizes links between actual transactions to finance and operations apps. The periodic process **Import from staging table** uses these records when creating Project Operations integration journal lines and Project invoice proposal lines.

Posting a Project Operations integration journal and a project invoice proposal triggers an update in respective records in the staging table, **ProjCDSActualsImport**. The system captures and records the following accounting attributes for actuals transactions:

- Accounting currency amount
- Exchange rate
- Voucher number
- Sales tax amount

The **Project Operations integration actuals** table map updates respective actuals records in Dataverse with this information.
