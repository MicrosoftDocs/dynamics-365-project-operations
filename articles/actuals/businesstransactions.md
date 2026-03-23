---
title: Business transactions in Project Operations 
description: This article provides an overview of the concept of business transactions in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 02/27/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava

---

# Business transactions in Project Operations

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations Core_

In Microsoft Dynamics 365 Project Operations, *business transaction* is an abstract concept that isn't represented by any entity. However, some common fields and processes on entities use the concept of business transactions. The following entities use this abstraction:

- Quote line details
- Contract line details
- Estimate lines
- Journal lines
- Actuals

Of these entities, Quote line details, Contract line details, and Estimate lines are mapped to the *estimation phase* in the project lifecycle. The Journal lines and Actuals entities are mapped to the *execution phase* in the project lifecycle.

Project Operations treats records in all five of these entities as business transactions. The only distinction is that records in the entities that are mapped to the estimation phase (Quote line details, Contract line details, and Estimate lines) are *financial forecasts*, whereas records in the entities that are mapped to the execution phase (Journal lines and Actuals) are *financial facts* that already occurred.

For more information, see [Estimates](../project-management/estimating-projects-overview.md) and [Actuals](actuals-overview.md).

## Concepts that are unique to business transactions

The following concepts are unique to the concept of business transactions:

- Transaction type
- Transaction class
- Transaction origin
- Transaction connection
- Source Document

### Transaction type

Transaction type represents the timing and context of the financial impact on a project. An option set defines it and supports the following values in Project Operations:

- Cost
- Project contract
- Unbilled sales
- Billed sales
- Inter organizational sales
- Resourcing unit cost

### Transaction class

Transaction class represents the different types of costs that projects incur. An option set defines it and supports the following values in Project Operations:

- Time
- Expense
- Material
- Fee
- Milestone
- Tax

> [!NOTE]
> The business logic for fixed-price billing in Project Operations typically uses the **Milestone** value.

### Transaction origin

Transaction origin is an entity that stores the origin and traceability links for business transactions to support reporting and lifecycle analysis. As project execution begins, each business transaction can create another business transaction, and the transaction origin records help build a trace of the relationships that result.

In addition, records that participate in the transaction lifecycle include a **Source document** polymorphic lookup that provides a direct reference back to the originating document for processing and navigation scenarios.

### Transaction connection

Transaction connection is an entity that stores the relationship between two related business transactions (for example, cost and related sales actuals, or reversals triggered by billing activities such as invoice confirmation or invoice corrections).

Transaction connection records include:
- Existing **text-based identifiers** (for example, fields that store the related record ID and record type as text). These fields remain for compatibility and existing reporting patterns.
- New **polymorphic lookup fields** that directly reference the related records. These lookups make processing and navigation simpler because they can point to different transaction tables without requiring separate fields per type.

### Source document

In addition to transaction origin and transaction connection records, Project Operations stores a **Source document** reference on records that participate in the transaction lifecycle.

- The **Source document** field is a **polymorphic lookup**, meaning it can reference different types of source records (for example, a time entry, expense entry, material usage log, or invoice-related record).
- This reference provides a direct, efficient way to identify the originating document for a record during processing and troubleshooting.

> Note: Transaction origin records continue to be created today for traceability and reporting scenarios. In the future, Project Operations will provide an option that allows customers to reduce or stop creating transaction origin records to help improve performance.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
