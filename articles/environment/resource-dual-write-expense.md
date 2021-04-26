---
title: Expense management integration
description: This topic provides information about expense report integration in Project Operations using dual-write. 
author: sigitac
ms.date: 4/26/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Expense management integration

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This topic provides information about expense reports integration in Project Operations [full expense deployment]../expense/expense-overview.md) using dual-write.

## Expense categories

In a full expense deployment, expense categories are created and maintained in Dynamics 365 Finance and Operations apps. To create a new expense category, complete the following steps:

1. In Dynamics 365 Dataverse, create a **Transaction** category. Dual-write integration will synchronize this transaction category to Finance and Operations apps. For more information, see [Configure project categories](/dynamics365/project-operations/project-accounting/configure-project-categories) and [Project Operations setup and configuration data integration](resource-dual-write-setup-integration.md). As a result of this integration, the system creates four shared category records in Finance and Operations apps.
2. In Finance, go to **Expense management** > **Setup** > **Shared categories** and select a shared category with an **Expense** transaction class. Set the parameter, **Can be used in Expense** to **True** and define the expense type to use.
3. Using this shared category record, create a new expense category by going to **Expense management** > **Setup** > **Expense categories** and selecting **New**. When the record is saved, dual-write uses the table map, **Project Operations integration project expense categories export entity (msdyn\_expensecategories)** to synchronize this record to Dataverse.

  ![Expense categories integration](./media/DW6ExpenseCategories.png)

Expense categories in Finance and Operations apps are company-, or legal entity-specific. There are separate, corresponding legal entity-specific records in Dataverse. When a project manager creates a new expense in Dataverse for a project created in Finance and Operations apps, only those expense categories that are in the **Owning company** field can be selected. 

When the Project manager records expense estimates in Dataverse **Project Details** form **Expense Estimates** tab, system allows to pick only expense categories matching this project owning company or without a reference to a company record.

## Expense reports

Expense reports are created and approved in Finance and Operations apps. For more information, see [Create and process expense reports in Dynamics 365 Project Operations](/learn/modules/create-process-expense-reports/). After the expense report is approved by the Project manager, it's posted to the general ledger. In Project Operations, project-related expense report lines are posted using special posting rules:

  - Project related cost (including non-recoverable tax) is not immediately posted to project cost account in general ledger, but instead is posted to expense integration account. This account is configured in Project management and accounting \&gt; Setup \&gt; Project management and accounting parameters, Project Operations on Dynamics 365 Customer engagement tab.
  - Dual-write synchronizes it to Dataverse using **Project Operations integration project expenses export entity (msdyn\_expenses)** table map.
  - Tax subledger, vendor subledger and other financial postings are recorded as applicable, at the time of expense report posting.

  ![Expense reports integration](./media/DW6ExpenseReports.png)

When a record is written to the **Expense** entity in Dataverse, the system triggers the automated approval process of the record. If needed, the automated approval process status can be reviewed in Dataverse by going to **Advanced settings** > **System** > **System jobs**. After approval is complete, expense transaction class records are created in the **Actuals** entity.

Expense related actuals are then processed using the dual-write table map **Project Operations integration actuals (msdyn\_actuals)**. For more information, see [Project estimates and actuals](resource-dual-write-estimates-actuals.md).

The periodic process, **Import from staging** creates Expense report-related journal lines in the Project Operations Integration journal. The offset account defaults to the expense integration account. The Posting integration journal clears the account balance for the expense transaction and moves the expense amount to the project cost account. The system also creates project subledger transactions for downstream invoicing and revenue recognition purposes.
