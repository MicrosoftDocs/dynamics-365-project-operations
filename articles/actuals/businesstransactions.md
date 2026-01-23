---
title: Business transactions in Project Operations 
description: This article provides an overview of the concept of business transactions in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 06/10/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava

---

# Business transactions in Project Operations

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations Core_

In Microsoft Dynamics 365 Project Operations, *business transaction* is an abstract concept that isn't represented by any entity. However, some common fields and processes on entities are designed to use the concept of business transactions. The following entities use this abstraction:

- Quote line details
- Contract line details
- Estimate lines
- Journal lines
- Actuals

Of these entities, Quote line details, Contract line details, and Estimate lines are mapped to the *estimation phase* in the project lifecycle. The Journal lines and Actuals entities are mapped to the *execution phase* in the project lifecycle.

Project Operations treats records in all five of these entities as business transactions. The only distinction is that records in the entities that are mapped to the estimation phase (Quote line details, Contract line details, and Estimate lines) are considered *financial forecasts*, whereas records in the entities that are mapped to the execution phase (Journal lines and Actuals) are considered *financial facts* that have already occurred.

For more information, see [Estimates](../project-management/estimating-projects-overview.md) and [Actuals](actuals-overview.md).

## Concepts that are unique to business transactions

The following concepts are unique to the concept of business transactions:

- Transaction type
- Transaction class
- Transaction origin
- Transaction connection

### Transaction type

Transaction type represents the timing and context of the financial impact on a project. It's defined by an option set that has the following supported values in Project Operations:

- Cost
- Project contract
- Unbilled sales
- Billed sales
- Inter organizational sales
- Resourcing unit cost

### Transaction class

Transaction class represents the different types of costs that are incurred on projects. It's defined by an option set that has the following supported values in Project Operations:

- Time
- Expense
- Material
- Fee
- Milestone
- Tax

> [!NOTE]
> The **Milestone** value is typically used by the business logic for fixed-price billing in Project Operations.

### Transaction origin

Transaction origin is an entity that stores the origin of each business transaction to help with reporting and traceability. As project execution begins, each business transaction creates another business transaction that will, in turn, create another business transaction, and so on.

### Transaction connection

Transaction connection is an entity that stores the relation between two similar business transactions, such as cost and related sales actuals or transaction reversals that are triggered by billing activities such invoice confirmation or invoice corrections.

Together, the Transaction origin and Transaction connection entities help you track relationships between business transactions and actions that caused a specific business transaction to be created.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
