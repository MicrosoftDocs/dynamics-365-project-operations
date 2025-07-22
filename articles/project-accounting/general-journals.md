---
title: Use general journals for advanced accounting
description: This article provides information about using general journals
author: ryansandness
ms.author: ryansandness
ms.date: 07/28/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---
Use general journals for advanced accounting
General journals are the all-purpose accounting feature in Dynamics 365 Finance. This document allows recording various financial transactions directly into the general ledger (GL). Common uses include daily accounting entries, adjustments, and integrations from external systems.

In the 10.0.45 release, a new preview feature is available, which enables the ability to create general journals against a project originating in Dataverse. This feature can be enabled from the **feature management** workspace with the feature named **Enable general journal entries for modern projects**.
One of the key capabilities of this feature is that the ledger offset account can be specified on the journal. Allowing for manual control off the offset enables users to have complete control of the accounting behind the expense. In addition, the journal framework provided many advanced capabilities such as workflow and approvals.

## Entering transactions

When entering journals, typically a user would enter a single line transaction with Project on the left for the account type and ledger on the right as the offset account. Entering the project details first before the offset creates a new expense against the project. Reversing the order creates a credit for the project.

An alternate way of entering journals is to create a project line with the debit but no offset and create a second line for the same voucher with a ledger credit.

When project is specified for the journal, a new project tab becomes available.

An amount can be entered in the debit or credit column to determine the cost price for the journal. Description is optional and flows though to Dataverse and onto the customer invoice. Currency for cost can be modified from the defaulted company currency. Once the account,  offset, and price are entered, we can click on the project tab to fill out the remaining required details.

On the Project tab, the fields to consider when creating an entry include:

- There's a new field introduced for **Contract line ID**. This field maps to the Dataverse contract line that allows expense entries or was selected based on task-based billing for the activity number.
- Activity number maps to task name for Project tasks and is optional.
- The category determines what posting account to use for the expense and defaults the line property value. The category defaults based on the Project management and accounting parameter for the Expense category within Project category defaults.
- Quantity can be defined.
- Cost price defaults to what you entered on the general tab earlier.
- Sales price always defaults to zero. You'll always have to define a cost price if necessary.
- Sales currency is locked to the contract currency.
General journals aren't aware of Dataverse pricing. The journals allow for manual entry of cost and/or sales. You may see the warning "Sales price not specified for time and material projects."

When we post the transaction, we commit cost immediately to general ledger and the project subeldger. This process doesn't use the expense integration account and instead posts immediately, unlike expense reports. We also connect to Dataverse through the IOrganization service and create a journal header and journal lines for each cost and sales amount in general journal. So for example, there might be one project expense journal line for 100 cost and 200 sales. This single journal with cost and sales ends up in Dataverse as two journal lines, with one line being 100 cost and one line being 200 sales. The journal is automatically posted in Dataverse.

The general journal has a journal voucher number in the header, such as USPM-000095 to uniquely identify it. This same voucher number carries through to the Dataverse journal header name.

Actuals are created in Dataverse, but only any unbilled sales lines are generated in the integration journal. Cost lines were already posted in Finance and were synced to Dataverse, but they don't come back through the integration journal. Once the import from staging completes, the sales line is imported and posted to complete the transaction in Finance.

## OneVoucher transactions for allocations

An alternate method to entering journals is possible by enabling [One voucher](https://learn.microsoft.com/en-us/dynamics365/finance/general-ledger/one-voucher). These transactions can have negative impacts on reporting, so should be thoroughly tested before enabling. These types of transactions allow for allocations or apportionment. For example, Contoso might want to purchase a piece of equipment for use for their organization. They have an expense for the equipment, but want to charge back 10% of it to each of 10 individual projects. Entering transactions in this way with several lines with different projects allow for a single voucher entry to be posted against multiple projects at the same time.

## Limitations

- While the feature is in preview, journals are limited to 50 project-related lines in the client for a total of 100 cost and sales lines at a time that can be included in a journal.
- Contract lines with multiple customers aren't considered. These sales lines might not generate unbilled sales correctly without the contract customer defined on the Dataverse journal line.
- Both modern projects and Project Management and Accounting (PMA) projects can't be used in the same journal when customers have previous projects and are [transitioning to using the modern architecture.](https://learn.microsoft.com/en-us/dynamics365/project-operations/prod-pma/move-to-modern-architecture)
