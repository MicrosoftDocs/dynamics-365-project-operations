---
title: Configure chargeable components of a project contract line
description: This article provides information about included, chargeable, and non-chargeable components on contract lines.
author: rumant
ms.date: 10/12/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Configure chargeable components of a project contract line

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A project-based contract line has the concept of included, chargeable, and non-chargeable components.

Included components are subject to the billing method, customer splits, not-to-exceed limits, and invoice frequency settings defined on the project-based contract line.

A subset of the included components can be marked as chargeable by updating the **Billing Type** field.

Chargeable components can be defined on roles, and transaction categories.

For a project contract line, the chargeability defined on a role only applies to the **Time** transaction class. If **Include Time** is set to **No** on a project contract line, the **Chargeable roles** tab isn't available.

Chargeability defined on transaction categories for a project contract line only applies to the **Expense** transaction class. If **Include Expenses** is set to **No** on a project contract line, the **Chargeable Categories** tab isn't available.

### Update a role to be chargeable or non-chargeable

A role can be chargeable or non-chargeable on specific project-based contract line.

On the **Chargeable roles** tab of a projec-based contract line, on the **Chargeable Categories** subgrid, in the **Billing Type** field, update the billing type for a role.

### Update a transaction category to be chargeable or non-chargeable

A transaction category can be chargeable or non-chargeable on a specific project-based contract line.

On the **Chargeable Categories** tab of a project-based contract line, on the **Chargeable Categories** subgrid, in the **Billing Type** field, update the billing type for a transaction.

### Resolve chargeability

An estimate or actual created for time will only be considered chargeable if time is included on the contract line, and if the role is configured as chargeable on the contract line.

An estimate or actual created for expense will only be considered chargeable if expense is included on the contract line, and if the transaction category is configured as chargeable on the contract line.

| Includes time | Includes expense | Role | Category | Task |
| --- | --- | --- | --- | --- |
| Yes | Yes | Chargeable | Chargeable | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non - Chargeable | Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non-Chargeable | Non-Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Non-Chargeable |
| No | Yes | Can't be set | Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual:Chargeable |
| No | Yes | Can't be set | Non-Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual: Non-chargeable |
| Yes | No | Chargeable | Can't be set | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Not available |
| Yes | No | Non-Chargeable | Can't be set | Billing on a time actual: Non-chargeable </br> Billing type on an expense actual: Not available |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
