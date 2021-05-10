---
title: Link actuals to original records
description: This topic explains how to link actuals to original records such as time entry, expense entry, or material usage logs.
author: rumant
ms.date: 03/25/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: rumant
---

# Link actuals to original records

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


In Dynamics 365 Project Operations, a *business transaction* is an abstract concept that isn't represented by an entity. However, some common fields and processes on entities are designed to use the concept of business transactions. The following entities use this concept:

- Quote line details
- Contract line details
- Estimate lines
- Journal lines
- Actuals

Of these entities, **Quote line details**, **Contract line details**, and **Estimate lines** are mapped to the estimate phase in the project lifecycle. The **Journal lines** and **Actuals entities** are mapped to the execution phase in the project lifecycle.

Project Operations recognizes records in these five entities as business transactions. The only distinction is that records in the entities that are mapped to the estimate phase are considered financial forecasts, whereas the records in entities that are mapped to the execution phase are considered financial facts that have already occurred.

## Concepts that are unique to business transactions
The following concepts are unique to the concept of business transactions:

- Transaction type
- Transaction class
- Transaction origin
- Transaction connection

### Transaction type

Transaction type represents the timing and context of the financial impact on a project. This is represented by an option set that has the following supported values in Project Operations:

  - Cost
  - Project contract
  - Unbilled sales
  - Billed sales
  - Inter organizational sales
  - Resourcing unit cost

### Transaction class

Transaction class represents the different types of costs that are incurred on projects. This is represented by an option set that has the following supported values in Project Operations:

  - Time
  - Expense
  - Material
  - Fee
  - Milestone
  - Tax

**Milestone** is typically used by the business logic for fixed-price billing in Project Operations.

### Transaction origin

**Transaction origin** is an entity that stores the origin of each business transaction. As a project gets underway, each business transaction will give rise to another business transaction which in turn will create another and so on. Transaction origin entity is designed to store data about each transaction’s origin to help with reporting and traceability. 

### Transaction connection

**ansaction connection** is an entity that stores the relationship between two similar business transactions, such as cost and related sales actuals, or transaction reversals triggered by billing activities such as invoice confirmation or invoice corrections.

Together, **Transaction origin** and **Transaction connection** help you track relationships between business transactions and actions that resulted in a specific business transaction.

### Example: How Transaction origin works with Transaction connection

The following example shows the typical processing of time entries in a Project Operations project lifecycle.

> ![Processing time entires in a Project Service life cycle](media/basic-guide-17.png)
 
1. A time entry submission creates two journal lines: one line for cost and one line for unbilled sales.
2. Eventual approval of the time entry creates two actuals: one actual for cost and one actual for unbilled sales.
3. When a new project invoice is created, the invoice line transaction is created by using data from the unbilled sales actual. 
4. When the invoice is confirmed, two new actuals are created: an unbilled sales reversal actual and a billed sales actual.

Each of these events creates a record in the **Transaction origin** and **Transaction connection** entities. These new records help build a history of relationships between the records that are created across time entry, journal line, actuals, and invoice line details.

The following table shows the records in the **Transaction origin** entity for the workflow.

| Event                        | Origin                   | Origin type                       | Transaction                       | Transaction type         |
|------------------------------|--------------------------|-----------------------------------|-----------------------------------|--------------------------|
| Time Entry Submission        | Time Entry Record GUID   | Time Entry                        | Journal Line Record GUID (cost)   | Journal Line             |
| Time entry Record GUID       | Time Entry               | Journal Line Record GUID (sales)  | Journal Line                      |                          |
| Time Approval                | Journal Line Record GUID | Journal Line                      | Unbilled Sales Record GUID        | Actual                   |
| Time entry Record GUID       | Time Entry               | Unbilled Sales Record GUID        | Actual                            |                          |
| Journal Line Record GUID     | Journal Line             | Cost Actual Record GUID           | Actual                            |                          |
| Time entry Record GUID       | Time Entry               | Cost Actual Record GUID           | Actual                            |                          |
| Invoice Creation             | Time Entry Record GUID   | Time Entry                        | Invoice Line Transaction GUID     | Invoice Line Transaction |
| Journal Line Record GUID     | Journal Line             | Invoice Line Transaction GUID     | Invoice Line Transaction          |                          |
| Invoice Confirmation         | Invoice Line GUID        | Invoice Line                      | Billed Sales Record GUID          | Actual                   |
| Invoice GUID                 | Invoice                  | Billed Sales Record GUID          | Actual                            |                          |
| Invoice Line Detail GUID     | Invoice Line Detail      | Billed Sales Record GUID          | Actual                            |                          |
| Time entry Record GUID       | Time Entry               | Billed Sales Record GUID          | Actual                            |                          |
| Journal Line Record GUID     | Journal Line             | Billed Sales Record GUID          | Actual                            |                          |
| Time entry Record GUID       | Time Entry               | Unbilled Sales Reversal GUID      | Actual                            |                          |
| Journal Line Record GUID     | Journal Line             | Unbilled Sales Reversal GUID      | Actual                            |                          |
| Draft Invoice Correction     | Old ILD GUID             | Invoice Line Transaction          | Correction ILD GUID               | Invoice Line Transaction |
| Old IL GUID                  | Invoice Line             | Correction ILD GUID               | Invoice Line Transaction          |                          |
| Old Invoice GUID             | Invoice                  | Correction ILD GUID               | Invoice Line Transaction          |                          |
| Time entry Record GUID       | Time Entry               | Correction ILD GUID               | Invoice Line Transaction          |                          |
| Journal Line Record GUID     | Journal Line             | Correction ILD GUID               | Invoice Line Transaction          |                          |
| Confirmed invoice correction | Old ILD GUID             | Invoice Line Transaction          | Reversed Billed Sales Actual GUID | Actual                   |
| Old IL GUID                  | Invoice Line             | Reversed Billed Sales Actual GUID | Actual                            |                          |
| Old Invoice GUID             | Invoice                  | Reversed Billed Sales Actual GUID | Actual                            |                          |
| Time entry Record GUID       | Time Entry               | Reversed Billed Sales Actual GUID | Actual                            |                          |
| Journal Line Record GUID     | Journal Line             | Reversed Billed Sales Actual GUID | Actual                            |                          |
| Old ILD GUID                 | Invoice Line Transaction | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Old IL GUID                  | Invoice Line             | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Old Invoice GUID             | Invoice                  | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Time entry Record GUID       | Time Entry               | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Journal Line Record GUID     | Journal Line             | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Correction ILD GUID          | Invoice Line Transaction | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Correction IL GUID           | Invoice Line             | New Unbilled Sales Actual GUID    | Actual                            |                          |
| Correction Invoice GUID      | Invoice                  | New Unbilled Sales Actual GUID    | Actual                            |                          |

The following table shows the records in the **Transaction connection** entity for the workflow.

| Event                          | Transaction 1                 | Transaction 1 role | Transaction 1 type           | Transaction 2                | Transaction 2 role | Transaction 2 type |
|--------------------------------|-------------------------------|--------------------|------------------------------|------------------------------|--------------------|--------------------|
| Time Entry Submission          | Journal Line (Sales) GUID     | Unbilled Sales     | msdyn_journalline            | Journal Line (cost) GUID     | Cost               | msdyn_journalline  |
| Time Approval                  | Unbilled Actual (Sales) GUID  | Unbilled Sales     | msdyn_actual                 | Cost Actual(cost) GUID       | Cost               | msdyn_actual       |
| Invoice Creation               | Invoice Line Detail GUID      | Billed Sales       | msdyn_invoicelinetransaction | Unbilled Sales Actual GUID   | Unbilled Sales     | msdyn_actual       |
| Invoice Confirmation           | Reversing Actual GUID         | Reversing          | msdyn_actual                 | Original unbilled sales GUID | Original           | msdyn_actual       |
| Billed Sales GUID              | Billed Sales                  | msdyn_actual       | Unbilled Sales Actual GUID   | Unbilled Sales               | msdyn_actual       |                    |
| Draft Invoice Correction       | Invoice Line Transaction GUID | Replacing          | msdyn_invoicelinetransaction | Billed Sales GUID            | Original           | msdyn_actual       |
| Confirm Invoice Correction     | Billed Sales Reversal GUID    | Reversing          | msdyn_actual                 | Billed Sales GUID            | Original           | msdyn_actual       |
| New Unbilled Sales Actual GUID | Replacing                     | msdyn_actual       | Billed Sales GUID            | Original                     | msdyn_actual       |                    |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
