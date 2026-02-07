---
title: Synchronize project expense categories between finance and operations and Project Service Automation
description: Learn how to synchronize project expense categories between Dynamics 365 Finance and Project Service Automation using templates and integration tasks.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0

---

# Synchronize project expense categories between finance and operations and Project Service Automation

[!include[banner](../includes/banner.md)]

This article describes the templates and underlying tasks that synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.

> [!NOTE]
>
> - Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.
> - Actuals integration is available in version 8.0.1 or later.
> - If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you can use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking. If you must reset the accounting distributions, we recommend that you also install KB 4131710.

## Data flow for Project Service Automation and Finance

The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance. The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.

If you master the project expense categories in Finance, the integration flow starts in Finance and goes to Project Service Automation. Synchronization from Project Service Automation to Finance updates the integration IDs of the project expense categories.

If you master the project expense categories in Project Service Automation, the integration flow starts in Project Service Automation and goes to Finance. The project categories must already be configured in Finance before the synchronization from Project Service Automation. Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again. In this way, you help guarantee that the categories are linked, and that no duplicates are created.

> [!NOTE]
> Typically, you master the project expense categories in Finance. However, if you don't, or if expense categories already exist in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template. Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template. You should then run the synchronization from Project Service Automation to Finance one more time.
>
> If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization runs:
>
> - The shared category that matches the project category that you set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.
> - For each Finance legal entity that you integrate with, the following project categories must exist:
>
>   - **Project category** exists.
>   - **Use in Expense** is enabled.
>   - **Active in journal** is enabled.
>   - **Transaction type** is set to **Expense**.

The following illustration shows how the data synchronizes between Project Service Automation and Finance.

:::image type="content" source="./media/ProjectExpenseCategoriesFlow.png" alt-text="Screenshot of data flow for Project Service Automation integration with Finance." lightbox="./media/ProjectExpenseCategoriesFlow.png":::

## Project expense category synchronization from Finance to Project Service Automation

### Template and task

To access the template, go to the Microsoft Power Apps admin center, select **Projects**, and then select **New project** in the upper-right corner to select public templates.

Use the following template and underlying task to synchronize project expense categories from Finance to Project Service Automation:

- **Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)
- **Name of the task in the project:** Sync categories to PSA

### Entity set

| Finance                           | Project Service Automation |
|-----------------------------------|----------------------------|
| Integration entity for categories | Transaction categories     |

### Entity flow

You manage project expense categories in Finance, and the system synchronizes these categories to Project Service Automation as transaction categories.

### Power Query

When you synchronize to Project Service Automation, use Microsoft Power Query for Excel to set the billing type on the transaction category. The **Project expense transaction categories (Fin and Ops to PSA)** template provides a default column and mapping. If you create your own template, add a conditional column in Power Query. Follow these steps:

1. Select the arrow to open the mapping of the project expense categories task in the **Project expense transaction categories (Fin and Ops to PSA)** template.
1. Select the **Advance Query and Filtering** link to open Power Query.
1. Select **Add Conditional Column**.
1. Enter a name for the new column, such as **BillingType**.
1. Enter the following condition: `if CATEGORYID not equal to null then 19235001, Otherwise null`.
1. Select **OK** on the column.
1. Map this new column on the mapping page.

The following illustration shows an example of the template task mapping in Data integration. The mapping shows the field information that synchronizes from Finance to Project Service Automation.

:::image type="content" source="./media/ProjectExpenseCategoriesToPSAMapping.jpg" alt-text="Screenshot of project expense category to Project Service Automation template mapping." lightbox="./media/ProjectExpenseCategoriesToPSAMapping.jpg":::

## Project expense category synchronization from Project Service Automation to Finance

### Template and task

Use the following template and underlying task to synchronize project expense categories from Project Service Automation to Finance:

- **Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)
- **Name of the task in the project:** Sync categories to Fin Ops

### Entity set

| Project Service Automation | Finance                           |
|----------------------------|-----------------------------------|
| Transaction categories     | Integration entity for categories |

### Entity flow

Finance manages project expense categories and synchronizes them to Project Service Automation as transaction categories. Synchronizing back to Finance updates the project category in Finance with the integration ID from Project Service Automation.

### Template mapping in Data integration

The following illustration shows an example of the template task mapping in Data integration.

> [!NOTE]
> The mapping shows the field information that synchronizes from Project Service Automation to Finance.

:::image type="content" source="./media/ProjectExpenseCategoriesToFinOpsMapping.jpg" alt-text="Screenshot of Project Service Automation to Finance template mapping." lightbox="./media/ProjectExpenseCategoriesToFinOpsMapping.jpg":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
