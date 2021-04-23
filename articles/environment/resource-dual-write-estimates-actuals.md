---
title: Project estimates and actuals integration
description: This topic provides information about Project Operations dual-write integration for project estimates and actuals.
author: sigitac
manager: Annbe
ms.date: 4/23/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Project estimates and actuals integration

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This topic provides information about Project Operations dual-write integration for project estimates and actuals.

# Project estimates

Project labor, expense and material estimates are created and maintained in Dataverse and synchronized to Finance and Operations apps for accounting purposes. Create, update, and delete operations are not supported through Finance and Operations apps.

Note that creating estimates require valid accounting configuration for the project. Projects associated with contract lines must have a valid project cost and revenue profile defined in Project cost and revenue profile rules. See [Configure accounting for billable projects | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/configure-accounting-billable-projects#configure-project-cost-and-revenue-profile-rules).

## Labor estimates

Labor estimates are created by Project Manager or Resource manager assigning generic or named resource to the project task. Resource assignment records can be reviewed by opening Project details in Dataverse and opening Resource assignments tab. Resource assignment records in Dataverse creates hour forecast records in Finance and Operations apps using **Project Operations integration entity for hour estimates (msdyn\_resourceassignments)**.

![Labor estimates integration](./Media/DW4LaborEstimates.png)

Dual-write synchronizes resource assignment records to the staging table (ProjCDSEstimateHoursImport), and then system uses business logic to create/ update hour forecast records (ProjForecastEmpl).

Project Accountant can review created forecast hour records in Finance and Operations apps by navigating to Project Management and Accounting \&gt; All projects \&gt; Plan \&gt; Hour forecasts.

## Expense estimates

Expense estimates are created by Project Manager in Project details form Expense estimates tab in Dataverse. Expense estimate records are stored in Estimate line entity in Dataverse. Such records will have transaction class Expense. Estimate line records (transaction class Expense) are synchronized to expense forecast records in Finance and Operations apps using **Project Operations integration entity for expense estimates (msdyn\_estimatelines)**.

![Expense estimates integration](./Media/DW4ExpenseEstimates.png)

Dual-write synchronizes expense estimate records to the staging table (ProjCDSEstimateExpenseImport), and then system uses business logic to create/ update expense forecast records (ProjForecastCost). Note that Estimate line stores sales estimate and cost estimate records separately. Business logic in Finance and Operations apps populates a single Expense forecast record using this detail in the staging table.

Project Accountant can review created expense forecast records in Finance and Operations apps by navigating to Project Management and Accounting \&gt; All projects \&gt; Plan \&gt; Expense forecasts.

## Material estimates

Material estimates are created by Project Manager in Project details form Material estimates tab in Dataverse. Material estimate records are stored in Estimate line entity in Dataverse. Such records will have transaction class Material. Estimate line records (transaction class Material) are synchronized to item forecast records in Finance and Operations apps using **Project integration table for material estimates (msdyn\_estimatelines)**.

![Material estimates integration](./Media/DW4MaterialEstimates.png)

Dual-write synchronizes material estimate records to the staging table (ProjForecastSalesImport), and then system uses business logic to create/ update item forecast records (ForecastSales). Note that Estimate line stores sales estimate and cost estimate records separately. Business logic in Finance and Operations apps populates a single Item forecast record using this detail in the staging table.

Project Accountant can review created item forecast records in Finance and Operations apps by navigating to Project Management and Accounting \&gt; All projects \&gt; Plan \&gt; Item forecasts.

# Project Actuals

Project Actuals are created in Dataverse, based on time, expense, material, and billing activity. All operational attributes of these transactions (i.e. quantity, cost price, sales price, project etc.) are captured in this Dataverse entity. See [Actuals | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/actuals/actuals-overview). Actual records are synchronized to Finance and Operations apps using dual-write table map **Project Operations integration actuals (msdyn\_actuals)** for downstream accounting.

![Actuals integration](./Media/DW4Actuals.png)

**Project Operations integration actuals** table map synchronizes all the records from Actuals entity in Dataverse, with the attribute **Skip Sync (internal use only)** set to False. This attribute value is set by Dataverse automatically at the time of record creation. Examples where this attribute is set to true are:

1. Project cost actuals for intercompany transactions. See [Create intercompany transactions | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/create-intercompany-transactions). These records are skipped, as system will recreate project cost actual in Finance and Operations apps at the time of intercompany vendor invoice is posted.
2. Negative unbilled sales records created at the time of proforma invoice confirmation. These records are skipped, as Project subledger in Finance and Operations apps does not reverse the unbilled sales record at the invoicing time but changes its status to Fully invoiced.

Dual-write table map synchronizes Actuals records to the staging table ( **ProjCDSActualsImport** ). These records then are processed by periodic process Import from staging table when creating Project Operations integration journal lines and Project invoice proposal lines. See [Integration journal in Project Operations | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/project-operations-integration-journal).

Dataverse also captures links between the Project actual transactions in Transaction connection entity. See [Link actuals to original records | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/actuals/linkingactuals). Links between actual transactions are also synchronized to Finance and Operations apps using dual-write table map Integration entity for project transaction relationships (msdyn\_transactionconnections). These records are used by periodic process Import from staging table when creating Project Operations integration journal lines and Project invoice proposal lines.

Posting Project Operations integration journal and Project invoice proposal triggers an update in respective records in the staging table ( **ProjCDSActualsImport** ). System captures and records the following accounting attributes for Actual transactions:

- Accounting currency amount
- Exchange rate
- Voucher number
- Sales tax amount

**Project Operations integration actuals** table map updates respective Actuals records in Dataverse with this detail.
