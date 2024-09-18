---
title: Journal line improvements
description: This article provides information about journal lines improvement feature in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 09/19/2024
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---
# Journal line improvements

_**Applies To:** Lite deployment - deal to proforma invoicing_

This feature helps prevent you from entering incorrect journal entries by enforcing business rules. It introduces new validations and automatically fills in dependent values based on the transaction class and type.

## Prerequisites
To use the journal line improvements feature in Dynamics 365 Project Operations, enable the feature **Enable journal line improvements** feature within the system.

| Billing method on contract line | Transaction type | Transaction classes allowed |Transaction classes not allowed |
 | --- | --- | --- | --- |
 | Fixed Price | Cost | Time, Expense, Material | Fee, Retainer and Milestone |
 |  | Unbilled sales | Retainer | Time, Expense, Material, Fee and Milestone |
 |  | Billed sales | Retainer and Milestone | Time, Expense, Material, Fee |
 |  | Inter Org Sales | Time, Expense | Material, Fee, Retainer and Milestone |
 |  | Resource unit cost | Time, Expense | Material, Fee, Retainer and Milestone |
 | Time & Material | Cost | Time, Expense, Material | Fee, Retainer and Milestone |
 |  | Unbilled sales | Time, Expense, Material, Fee, Retainer | Milestone |
 |  | Billed sales | Time, Expense, Material, Fee, Retainer | Milestone |
 |  | Inter Org Sales | Time, Expense | Material, Fee, Retainer and Milestone |
 |  | Resource unit cost | Time, Expense | Material, Fee, Retainer and Milestone |
