---
# required metadata

title: Business Transactions in Project Operations 
description: This topic provides an overview of the concept of business transactions in Project Operations.
author: rumant
ms.date: 01/31/2022
ms.topic: overview
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: tonyafehr
ms.search.scope: 
# ms.tgt_pltfrm: 

ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: rumant
ms.search.validFrom: 2022-01-31
---

# Business Transactions in Project Operations

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, *business transaction* is an abstract concept that isn't represented by any entity. However, some common fields and processes on entities are designed to use the concept of business transactions. The following entities use this abstraction:

- Quote line details
- Contract line details
- Estimate lines
- Journal lines
- Actuals

Of these entities, Quote line details, Contract line details, and Estimate lines are mapped to the estimation phase in the project lifecycle. The Journal lines and Actuals entities are mapped to the execution phase in the project lifecycle.

Project Operations treats records in these five entities as business transactions. The only distinction is that records in entities that are mapped to the estimation phase are considered financial forecasts, whereas the records in entities that are mapped to the execution phase are considered financial facts that have already occurred.

For more information, see [Estimates](../project-management/estimating-projects-overview.md) and [Actuals](actuals-overview.md).

## Concepts that are unique to business transactions
The following concepts are unique to the concept of business transactions:

- Transaction type
- Transaction class
- Transaction origin
- Transaction connection

### Transaction type

Transaction type represents the timing and context of the financial impact on a project. It's represented by an option set that has the following supported values in Project Operations:
- Cost
- Project contract
- Unbilled sales
- Billed sales
- Inter organizational sales
- Resourcing unit cost

### Transaction class

Transaction class represents the different types of costs that are incurred on projects. It's represented by an option set that has the following supported values in Project Operations:

- Time
- Expense
- Material
- Fee
- Milestone
- Tax

The **Milestone** value is typically used by the business logic for fixed-price billing in Project Operations.

### Transaction origin

Transaction origin is an entity that stores the origin of each business transaction. As project execution gets underway, each business transaction will give rise to another business transaction which in turn will create another and so on. Transaction origin entity was designed to store data about each transaction’s origin to help reporting and traceability. 

### Transaction connection

Transaction connection is an entity that stores the relation between two similar business transactions such as cost and related sales actuals or transaction reversals triggered by billing activities such invoice confirmation or invoice corrections.

Together, Transaction origin and Transaction connection help you keep track of relationships between business transactions and actions that resulted in the creation of a specific business transaction.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
