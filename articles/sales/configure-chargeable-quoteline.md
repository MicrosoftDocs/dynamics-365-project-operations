---
title: Configure the chargeable components of a project-based quote line
description: Learn how to configure chargeable and non-chargeable components for project-based quote lines, including roles, transaction categories, and billing types.
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Configure the chargeable components of a project-based quote line

_**Applies To:** Project Operations Integrated with ERP_

A project-based quote line can include components and chargeable components.

Included components are subject to the billing method, customer splits, not-to-exceed limits, and invoice frequency settings that you define on the project-based quote line.
You can mark a subset of the included components as chargeable by using **Billing Type**. In the **Billing Type** field, select one of the following options in the context of a quote line:

- Chargeable
- Non-chargeable

Define chargeable components on roles and transaction categories.

Chargeability that you define on roles for a project quote line only applies to the **Time** transaction class. If a project quote line has **Include Time** = **No**, the **Chargeable Roles** tab isn't available.

Chargeability that you define on transaction categories for a project quote line only applies to the **Expense** transaction class. If a project quote line has **Include Expenses** = **No**, the **Chargeable Categories** tab isn't available.

## Update a role to be chargeable or non-chargeable

A role can be chargeable or non-chargeable on a project-based quote line. Configure the billing type on a role by using the **Chargeable Roles** tab of a project-based quote line. Update **Billing Type** on the **Chargeable Roles** subgrid.

## Update a transaction category to be chargeable or non-chargeable

A transaction category can be chargeable or non-chargeable on a project-based quote line. Configure the billing type on a transaction by using the **Chargeable Categories** tab of a project-based quote line. Update the **Billing Type** field on the **Chargeable Categories** subgrid.

## Resolve chargeability

An estimate or actual created for time is chargeable only if the quote line includes the time and the role is configured as chargeable.
An estimate or actual created for an expense is chargeable only if the quote line includes the expense and the transaction category is configured as chargeable on the quote line. The following table shows how chargeability defaults on each actual. The defaults are based on the included components and the billing type that you set up on the quote line.

| Includes time | Includes expense | Role | Category | Task |
| --- | --- | --- | --- | --- |
| Yes | Yes | Chargeable | Chargeable | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non - Chargeable | Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non-Chargeable | Non-Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Non-Chargeable |
| No | Yes | Can't be set | Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual: Chargeable |
| No | Yes | Can't be set | Non-Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual: Non-chargeable |
| Yes | No | Chargeable | Can't be set | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Not available |
| Yes | No | Non-Chargeable | Can't be set | Billing on a time actual: Non-chargeable </br> Billing type on an expense actual: Not available |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
