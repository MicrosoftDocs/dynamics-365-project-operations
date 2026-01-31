---
title: Synchronize project actuals directly from Project Service Automation to the project integration journal for posting in finance and operations
description: This article describes the templates and underlying tasks that are used to synchronize project actuals directly from Microsoft Dynamics 365 Project Service Automation to finance and operations.
author: suvaidya
ms.author: nshrivastava
ms.date: 06/10/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0

---
# Synchronize project actuals directly from Project Service Automation to the project integration journal for posting in finance and operations

[!include[banner](../includes/banner.md)]

This article describes the templates and underlying tasks that are used to synchronize project actuals directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.

The template synchronizes transactions from Project Service Automation into a staging table in Finance. After synchronization is completed, you **must** import the data from the staging table into the integration journal.

> [!NOTE]
>
> - Project actuals integration is available starting in version 8.0.1.
> - If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you can use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking. If you must reset the accounting distributions, install KB 4131710.
> - If you're using version 7.3.0 and you're bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.
> - If you're entering sales tax amounts on time or expense transactions in Project Service Automation, you must install Project Service Automation Update 7. Otherwise, the tax actuals aren't linked to the associated time or expense actuals, and they aren't synchronized to Finance. For more information, contact Support.

## Data flow for Project Service Automation to Finance

The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance. The integration templates that are available with the Data integration feature enable the flow of data about project actuals from Project Service Automation to Finance.

The following illustration shows how the data is synchronized between Project Service Automation and Finance.

:::image type="content" source="./media/ProjectActualsFlow.jpg" alt-text="Screenshot of data flow for Project Service Automation integration with finance and operations." lightbox="./media/ProjectActualsFlow.jpg":::

## Project actuals from Project Service Automation

### Template and tasks

To access the available templates, in the Microsoft Power Apps admin center, select **Projects**. In the upper-right corner, select **New project** to select public templates.

Use the following template and underlying tasks to synchronize project actuals from Project Service Automation to Finance:

- **Name of the template in Data integration:** Project actuals (PSA to Fin and Ops)
- **Name of the tasks in the project:**

  - Actuals
  - TransactionConnections

### Entity set

| Project Service Automation | Finance                                   |
|----------------------------|----------------------------------------------------------|
| Actuals                    | Integration entity for project actuals                   |
| Transaction Connections    | Integration entity for project transaction relationships |

### Entity flow

Project actuals are managed in Project Service Automation, and the synchronization sends them to the project integration journal in Finance. The accounting uses default financial dimensions and the posting setup.

### Prerequisites

Before you can synchronize actuals, configure the Project Service Automation integration parameters and synchronize projects, project tasks, and project expense transaction categories.

### Power Query

In the project actuals template, use Microsoft Power Query for Excel to complete these tasks:

- Transform the transaction type in Project Service Automation to the correct transaction type in Finance. The Project actuals (PSA to Fin and Ops) template already defines this transformation.
- Transform the billing type in Project Service Automation to the correct billing type in Finance. The Project actuals (PSA to Fin and Ops) template already defines this transformation. The billing type is then mapped to the line property, based on the configuration on the **Project Service Automation integration parameters** page.
- Filter to specific resource organizational units that must be synchronized with this template.
- If you synchronize intercompany time or intercompany expense actuals to Finance, transform the contract organizational unit to the correct legal entity in Finance. In the Project actuals (PSA to Fin and Ops) template, a conditional column is defined based on demo data. Update the last inserted conditional column to the correct legal entities. Otherwise, either an integration error might occur, or incorrect actual transactions might be imported into Finance.
- If you don't synchronize intercompany time or intercompany expense actuals to Finance, delete the last inserted conditional column from your template. Otherwise, either an integration error might occur, or incorrect actual transactions might be imported into Finance.

#### Contract organizational unit

To update the inserted conditional column in the template, select the **Map** arrow to open the mapping. Select the **Advanced Query and Filtering** link to open Power Query.

- If you're using the default Project actuals (PSA to Fin and Ops) template, in Power Query, select the last **Inserted Condition** from the **Applied Steps** section. In the **Function** entry, replace **USSI** with the name of the legal entity that should be used with the integration. Add additional conditions to the **Function** entry as you require, and update the **else** condition from **USMF** to the correct legal entity.
- If you're creating a new template, add the column to support intercompany time and expenses. Select **Add Conditional Column**, and enter a name for the column, such as **LegalEntity**. Enter a condition for the column, where, if **msdyn\_contractorganizationalunitid.msdyn\_name** is \<organizational unit\>, then \<enter the legal entity\>; else null.

### Template mapping in Data integration

The following illustrations show an example of the template task mapping in Data integration. The mapping shows the field information that synchronizes from Project Service Automation to Finance.

:::image type="content" source="./media/ActualsMapping.jpg" alt-text="Screenshot of template mapping for Actuals." lightbox="./media/ActualsMapping.jpg":::

:::image type="content" source="./media/TransactionConnections.jpg" alt-text="Screenshot of template mapping for Transaction connections." lightbox="./media/TransactionConnections.jpg":::

## Import from staging table after integration from Project Service Automation

Run the Import from staging table periodic process after you synchronize actuals from Project Service Automation to Finance. This process imports the project transactions from the staging table into the Project Service Automation integration journal, where the accounting is applied and the imported transactions can be posted. Run this process in batch mode. You can optionally set up the process to run as a recurring batch.

## Update actuals from Finance

### Template and tasks

Use the following template and tasks to synchronize the voucher number and sales taxes for posted project transactions from Finance to Project Service Automation:

- **Name of the template in Data integration:** Project actuals update (Fin Ops to PSA)
- **Name of the tasks in the project:**

  - Actuals
  - TransactionConnections

### Entity set

| Finance                                                  | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Integration entity for project actuals                   | Actuals                    |
| Integration entity for project transaction relationships | Transaction Connections    |

### Entity flow

Project Service Automation manages project actuals and synchronizes them to the project integration journal in Finance. After you post actuals in Finance, the system updates them in Project Service Automation with the voucher number from Finance. If you add sales taxes in Finance, the system creates new tax actuals in Project Service Automation.

### Power Query

In the project actuals update template, use Power Query to complete these tasks:

- Transform the transaction type in Finance to the correct transaction type in Project Service Automation. This transformation is already defined in the Project actuals update (Fin Ops to PSA) template.
- Transform the billing type in Finance to the correct billing type in Project Service Automation. This transformation is already defined in the Project actuals update (Fin Ops to PSA) template.

### Template mapping in Data integration

The following illustrations show examples of the template task mappings in Data integration. The mapping shows the field information that synchronizes from Finance to Project Service Automation.

:::image type="content" source="./media/ActualsUpdateMapping.jpg" alt-text="Screenshot of template mapping for Actuals update." lightbox="./media/ActualsUpdateMapping.jpg":::

:::image type="content" source="./media/TransactionConnectionsUpdate.jpg" alt-text="Screenshot of template mapping for Transaction update." lightbox="./media/TransactionConnectionsUpdate.jpg":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
