---
title: Expense management integration
description: This topic provides information about expense reports integration in Project Operations full expense deployment using dual-write. 
author: sigitac
manager: Annbe
ms.date: 4/23/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Project Operations setup and configuration data integration

_**Applies To:** Project Operations for resource/non-stocked based scenarios_
This topic provides information about expense reports integration in Project Operations [full expense deployment](https://docs.microsoft.com/en-us/dynamics365/project-operations/expense/expense-overview#full) using dual-write.

# Expense categories

In full expense deployment, expense categories are created and maintained in Finance and Operations apps. Steps to create a new expense category:

1. Create Transaction category in Dataverse. Dual-write integration will synchronize this transaction category to Finance and Operations apps. See [Configure project categories | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/configure-project-categories) and [Project Operations setup and configuration data integration | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-setup-integration) for more information. As a result of this integration, system will create four Shared category records in Finance and Operations apps.
2. Navigate to Expense management \&gt; Setup \&gt; Shared categories and select Shared category with Expense transaction class. Set parameter Can be used in Expense to true and define Expense type to be used.
3. Create Expense category using this Shared category record in Expense management \&gt; Setup \&gt; Expense categories. When the record is saved, dual-write uses table map **Project Operations integration project expense categories export entity (msdyn\_expensecategories)** to synchronize this record to Dataverse.

![Expense categories integration](./media/DW6ExpenseCategories.png)

Expense categories in Finance and Operations apps are company (legal entity) specific and will create separate corresponding, legal entity specific records in Dataverse. When Project Manager records expense estimates in Dataverse Project details form Expense estimates tab, system allows to pick only expense categories matching this project owning company or without a reference to a company record.

# Expense reports

Expense reports are created and approved in Finance and Operations apps. See [Create and process expense reports in Dynamics 365 Project Operations - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/create-process-expense-reports/) for more details. After expense report is approved by Project manager, it is posted to the general ledger. In Project Operations for resource based/ non stocked scenarios, project related expense report lines are posted using special posting rules:

1. Project related cost (including non-recoverable tax) is not immediately posted to project cost account in general ledger, but instead is posted to expense integration account. This account is configured in Project management and accounting \&gt; Setup \&gt; Project management and accounting parameters, Project Operations on Dynamics 365 Customer engagement tab.
2. Dual-write synchronizes it to Dataverse using **Project Operations integration project expenses export entity (msdyn\_expenses)** table map.
3. Tax subledger, vendor subledger and other financial postings are recorded as applicable, at the time of expense report posting.

![Expense reports integration](./media/DW6ExpenseReports.png)

As record gets written to Expense entity in Dataverse, system triggers automated approval process of this record. If needed, automated approval process status can be reviewed in Dataverse by navigating to Advanced settings \&gt; System \&gt; System jobs. Once approval is complete, system creates expense transaction class records in the Actuals entity.

Expense related actuals are then processed using dual-write table map **Project Operations integration actuals (msdyn\_actuals)**. See [Project estimates and actuals]( resource-dual-write-estimates-actuals.md) for more details.

**Import from staging** periodic process creates Expense report related Project Operations integration journal lines. Offset account is defaulted to Expense integration account. Posting integration journal, clears this account balance for the expense transaction and moves expense amount to project cost account. System also creates Project subledger transactions for downstream invoicing and revenue recognition purposes.
