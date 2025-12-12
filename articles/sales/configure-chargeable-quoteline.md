---
title: Configure the chargeable components of a project-based quote line
description: This article provides information about included, chargeable, and non-chargeable components on project-based quote lines.
author: rumant
ms.date: 11/18/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Configure the chargeable components of a project-based quote line

_**Applies To:** Project Operations Integrated with ERP_

A project-based quote line can have included components and chargeable components.

Included components are subject to the billing method, customer splits, not-to-exceed limits, and invoice frequency settings defined on the project-based quote line.
A subset of the included components can be marked as chargeable by using **Billing Type**. You can select one of the following options in the **Billing Type** field in the context of a quote line:

   - Chargeable
   - Non-chargeable

Chargeable components can be defined on roles and transaction categories.

Chargeability that is defined on roles for a project quote line only applies to the **Time** transaction class. If a project quote line has **Include Time** = **No**, the **Chargeable Roles** tab isn't available.

Chargeability that is defined on transaction categories for a project quote line only applies to the **Expense** transaction class. If a project quote line has **Include Expenses** = **No**, the **Chargeable Categories** tab isn't available.

## Update a role to be chargeable or non-chargeable
A role can be chargeable or non-chargeable on a project-based quote line. The billing type on a role can be configured on the **Chargeable Roles** tab of a project-based quote line. To do this, update **Billing Type** on the **Chargeable Roles** subgrid. 

## Update a transaction category to be chargeable or non-chargeable
A transaction category can be chargeable or non-chargeable on a project-based quote line. The billing type on a transaction can be configured on the **Chargeable Categories** tab of a project-based quote line. To do this, update the **Billing Type** field on the **Chargeable Categories** subgrid. 

## Resolve chargeability

An estimate or actual created for time will only be considered chargeable if the time is included on the quote line and if the role is configured as chargeable.
An estimate or actual created for an expense will only be considered chargeable if the expense is included on the quote line and if the transaction category is configured as chargeable on the quote line. The following table shows how chargeability defaults on each actual. The defaults are based on the included components and the billing type that is set up on the quote line.

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