---
title: Project estimates and actuals integration
description: This article provides information about Project Operations dual-write integration for project estimates and actuals.
author: suvaidya
ms.author: suvaidya
ms.date: 06/10/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project estimates and actuals integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article provides information about Project Operations dual-write integration for project estimates and actuals.

## Project estimates

Project labor, expense, and material estimates are created and maintained in Microsoft Dataverse and synchronized to finance and operations apps for accounting purposes. Create, update, and delete operations aren't supported through the finance and operations apps.

Creating estimates requires a valid accounting configuration for the project. Projects that are associated with contract lines must have a valid project cost and revenue profile defined in the Project cost and revenue profile rules. For more information, see [Configure accounting for billable projects](../project-accounting/configure-accounting-billable-projects.md#configure-project-cost-and-revenue-profile-rules).

## Labor estimates

Labor estimates are created by the Project Manager or Resource manager who also assigns a generic or named resource to the project task. Resource assignment records can be reviewed on the **Resource Assignments** tab on the **Project Details** page in Dataverse. Resource assignment records in Dataverse create hour forecast records in finance and operations apps using **Project Operations integration entity for hour estimates (msdyn\_resourceassignments)**.

   ![Labor estimates integration.](./Media/DW4LaborEstimates.png)

Dual-write synchronizes resource assignment records to the staging table (**ProjCDSEstimateHoursImport**), and then uses business logic to create and update hour forecast records (**ProjForecastEmpl**).

The Project accountant reviews forecast hour records created in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Hour forecasts**.

## Expense estimates

Expense estimates are created by the Project manager on the **Expense Estimates** tab on the **Project Details** page in Dataverse. Expense estimate records are stored in the **Estimate Line** entity in Dataverse. These estimate records have transaction class, **Expense** and are synchronized to expense forecast records in finance and operations apps using **Project Operations integration entity for expense estimates (msdyn\_estimatelines)**.

   ![Expense estimates integration.](./Media/DW4ExpenseEstimates.png)

Dual-write synchronizes expense estimate records to the staging table, **ProjCDSEstimateExpenseImport)** and then uses business logic to create and update expense forecast records (**ProjForecastCost**). Estimate lines store sales estimate and cost estimate records separately. The business logic in finance and operations apps populates a single Expense forecast record using this detail in the staging table.

The Project accountant can review expense forecast records in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Expense forecasts**.

## Material estimates

Material estimates are created by the Project manager on the **Material Estimates** tab on the **Project Details** page in Dataverse. Material estimate records are stored in the **Estimate Line** entity in Dataverse. These estimate records have the transaction class, **Material** and are synchronized to item forecast records in finance and operations apps using **Project integration table for material estimates (msdyn\_estimatelines)**.

   ![Material estimates integration.](./Media/DW4MaterialEstimates.png)

Dual-write synchronizes material estimate records to the staging table **ProjForecastSalesImpor**, and then uses business logic to create and update item forecast records (**ForecastSales**). Estimate lines store sales estimate and cost estimate records separately. The business logic in finance and operations apps populates a single Item forecast record using this detail in the staging table.

The Project accountant can review item forecast records in finance and operations apps by going to **Project management and accounting** > **All projects** > **Plan** > **Item forecasts**.

## Project actuals

Project actuals are created in Dataverse, based on time, expense, material, and billing activity. All operational attributes of these transactions including quantity, cost price, sales price, and project are captured in this Dataverse entity. For more information, see [Actuals](../actuals/actuals-overview.md). Actual records are synchronized to finance and operations apps using the dual-write table map **Project Operations integration actuals (msdyn\_actuals)** for downstream accounting.

   ![Actuals integration.](./Media/DW4Actuals.png)

The **Project Operations integration actuals** table map synchronizes all the records from the **Actuals** entity in Dataverse, with the attribute **Skip Sync (internal use only)** set to **False**. This attribute value is set in Dataverse automatically when the record is created. Examples where this attribute is set to **True** are:

  - Project cost actuals for intercompany transactions. For more information, see [Create intercompany transactions](../project-accounting/create-intercompany-transactions.md). These records are skipped because the system recreates the project cost actual in finance and operations apps when the intercompany vendor invoice is posted.
  - Negative unbilled sales records created when the proforma invoice is confirmed. These records are skipped because the project subledger in finance and operations apps doesn't reverse the unbilled sales record at invoicing but changes the status to fully invoiced.

The dual-write table map synchronizes the actuals records to the staging table, **ProjCDSActualsImport**. These records are processed by the periodic process **Import from staging table** when creating Project Operations integration journal lines and project invoice proposal lines. For more information, see [Integration journal in Project Operations](../project-accounting/project-operations-integration-journal.md).

Dataverse also captures the links between the project actual transactions in the **Transaction connection** entity. For more information, see [Link actuals to original records](../actuals/linkingactuals.md). Links between actual transactions are also synchronized to finance and operations apps using the dual-write table map, **Integration entity for project transaction relationships (msdyn\_transactionconnections)**. These records are used by the periodic process, **Import from staging table** when creating Project Operations integration journal lines and Project invoice proposal lines.

Posting a Project Operations integration journal and a project invoice proposal triggers an update in respective records in the staging table, **ProjCDSActualsImport**. The system captures and records the following accounting attributes for actuals transactions:

- Accounting currency amount
- Exchange rate
- Voucher number
- Sales tax amount

The **Project Operations integration actuals** table map updates respective actuals records in Dataverse with this information.
