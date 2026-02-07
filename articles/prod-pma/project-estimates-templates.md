---
title: Synchronize project estimates directly from Project Service Automation to finance and operations
description: Learn how to synchronize project hour and expense estimates from Dynamics 365 Project Service Automation to Finance with step-by-step templates and tasks.
author: abriccetti
ms.author: abriccetti
ms.date: 02/06/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
audience: Application User
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
---

# Synchronize project estimates directly from Project Service Automation to finance and operations

[!include[banner](../includes/banner.md)]

This article describes the templates and underlying tasks that you use to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.

> [!NOTE]
>
> - Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.
> - Actuals integration is available in version 8.0.1 or later.

## Data flow for Project Service Automation to Finance

The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance. The integration templates that are available by using the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.

The following illustration shows how the data synchronizes between Project Service Automation and Finance.

:::image type="content" source="./media/ProjectEstimatesFlow.png" alt-text="Screenshot of data flow for Project Service Automation integration with Finance." lightbox="./media/ProjectEstimatesFlow.png":::

## Project hour estimates

### Template and tasks

To access the available templates, in the Microsoft Power Apps admin center, select **Projects**. In the upper-right corner, select **New project** to select public templates.

Use the following template and underlying tasks to synchronize project hour estimates from Project Service Automation to Finance:

- **Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)
- **Name of the tasks in the project:**

  - Transaction relationships
  - Expense estimates

### Entity set

| Project Service Automation | Finance                                       |
|----------------------------|-----------------------------------------------|
| Project tasks              | Integration entity for project hour estimates |

### Entity flow

Project hour estimates are managed in Project Service Automation, and they're synchronized to Finance as project hour forecasts.

### Prerequisites

Before you can synchronize project hour estimates, synchronize projects, project tasks, and project expense transaction categories.

### Power Query

In the project hour estimates template, use Microsoft Power Query for Excel to complete these tasks:

- Set the default forecast model ID that the integration uses when it creates new hour forecasts.
- Filter out any resource-specific records in the task that cause the integration to fail when it imports hour forecasts.
- Filter out any empty transaction category rows. Failure to complete this task might result in incorrect hour forecasts.

#### Set the default forecast model ID

To update the default forecast model ID in the template, select the **Map** arrow to open the mapping. Then select the **Advanced Query and Filtering** link.

- If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**. In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that the integration should use. The default template has a forecast model ID from the demo data.
- If you're creating a new template, add this column. In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**. Enter the condition for the column, where, if Project task isn't null, then \<enter the forecast model ID\>; else null.

#### Filter out resource-specific records

The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records. If you create your own template, add this filter. Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.

#### Filter out empty transaction category rows

Add a filter to remove any rows that have empty transaction categories. This task is required, regardless of whether you're using the default template or creating your own template. This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect. Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.

### Template mapping in Data integration

The following illustration shows an example of the template task mapping in Data integration. The mapping shows the field information that synchronizes from Project Service Automation to Finance.

:::image type="content" source="./media/ProjectHourEstimatesMapping.jpg" alt-text="Screenshot of template task mapping in data integration." lightbox="./media/ProjectHourEstimatesMapping.jpg":::

## Project expense estimates

### Template and tasks

Use the following template and underlying tasks to synchronize project expense estimates from Project Service Automation to Finance:

- **Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)
- **Name of the tasks in the project:**

  - Transaction relationships
  - Expense estimates

### Entity set

| Project Service Automation | Finance                                                  |
|----------------------------|----------------------------------------------------------|
| Transaction Connections    | Integration entity for project transaction relationships |
| Estimate Lines             | Integration entity for project expense estimates         |

### Entity flow

Project Service Automation manages project expense estimates. The system synchronizes these estimates to Finance as project expense forecasts.

### Prerequisites

Before you can synchronize project expense estimates, synchronize projects, project tasks, and project expense transaction categories.

### Power Query

In the project expense estimates template, use Power Query to complete the following tasks:

- Filter to include only expense estimate line records.
- Set the default forecast model ID that the integration uses when it creates new hour forecasts.
- Transform the billing types.
- Transform the transaction types.

#### Filter to include only expense estimate lines

The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration. If you create your own template, add this filter. Select the **Transaction relationships** task, and then select the **Map** arrow to open the mapping. Select the **Advanced Query and Filtering** link. Filter the **msdyn_transactiontype1** column so that it includes only **msdyn_estimateline**.

#### Set the default forecast model ID

To update the default forecast model ID in the template, select the **Expense estimates** task, and then select the **Map** arrow to open the mapping. Select the **Advanced Query and Filtering** link.

- If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section. In the **Function** entry, replace **O_forecast** with the name of the forecast model ID that should be used with the integration. The default template has a forecast model ID from the demo data.
- If you're creating a new template, add this column. In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**. Enter the condition for the column, where, if Estimate line ID isn't null, then \<enter the forecast model ID\>; else null.

#### Transform the billing types

The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that's used to transform the billing types that the integration receives from Project Service Automation. If you create your own template, add this conditional column. Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**. Enter a name for the new column, such as **BillingType**. Then enter the following condition:

If **msdyn_billingtype** = 192350000, then **NonChargeable**  
else if **msdyn_billingtype** = 192350001, then **Chargeable**  
else if **msdyn_billingtype** = 192350002, then **Complimentary**  
else **NotAvailable**

#### Transform the transaction types

The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that's used to transform the transaction types that the integration receives from Project Service Automation during the integration. If you create your own template, add this conditional column. Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**. Enter a name for the new column, such as **TransactionType**. Then enter the following condition:

If **msdyn_transactiontypecode** = 192350000, then **Cost**  
else if **msdyn_transactiontypecode** = 192350005, then **Sales**  
else **null**

### Template mapping in Data integration

The following illustrations show examples of the template task mappings in Data integration. The mapping shows the field information that synchronizes from Project Service Automation to Finance.

:::image type="content" source="./media/ExpenseEstimateTransactionRelationshipsMapping.jpg" alt-text="Screenshot of template mapping of expense estimate transactions." lightbox="./media/ExpenseEstimateTransactionRelationshipsMapping.jpg":::

:::image type="content" source="./media/ExpenseEstimatesMapping.jpg" alt-text="Screenshot of template mapping of expense estimates." lightbox="./media/ExpenseEstimatesMapping.jpg":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
