---
title: Configure chargeable components of a project-based Quote line
description: This topic provides information about included, chargeable, and non-chargeable components on project-based quote lines.
author: rumant
manager: Annbe
ms.date: 10/12/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: stsporen
---

# Configure chargeable components of a project-based quote line

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A project-based quote line has the concept of included components and chargeable components.
Included components are all components that will be subject to the billing method and customer splits, not-to-exceed limits and invoice frequency settings defined on the project-based quote line.
A sub-set of the included components can be marked as chargeable using the Billing Type field. Billing Type field is an option-set that allows the following values in the context of a quote line:

•	Chargeable

•	Non-chargeable

Chargeable components can be defined on roles and transaction categories.

Chargeability defined on Roles for a project quote line only applies to Time transaction class. If a project quote line has Include Time = No, then you will not see the tab for “Chargeable roles”.

Chargeability defined on Transaction categories for a project quote line only applies to Expense transaction class. If a project quote line has Include Expenses = No, then you will not see the tab for “Chargeable Categories”.

## Updating a Role to be chargeable or non-chargeable
A role can be chargeable or non-chargeable in the context of a specific project-based quote line. 
Billing type on a role can be configured on chargeable roles tab of a Project – based quote line by updating Billing type field on the Chargeable roles sub-grid. 

## Updating a Transaction category to be chargeable or non-chargeable
A transaction category can be chargeable or non-chargeable in the context of a specific project-based quote line. 
Billing type on a transaction can be configured on chargeable categories tab of a Project – based quote line by updating Billing type field on the Chargeable categories sub-grid. 

## Resolving chargeability

An estimate or actual created for time will only be considered Chargeable if time is included on the Quote line and if the Role is configured as Chargeable on the Quote line.
An estimate or actual created for expense will only be considered Chargeable if Expense is included on the Quote line and if the Transaction category is configured as Chargeable on the Quote line.

| Includes time | Includes expense | Role | Category | Task |
| --- | --- | --- | --- | --- |
| Yes | Yes | Chargeable | Chargeable | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non - Chargeable | Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Chargeable |
| Yes | Yes | Non-Chargeable | Non-Chargeable | Billing on a time actual: Non-Chargeable </br>Billing type on an expense actual: Non-Chargeable |
| No | Yes | Can't be set | Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual:Chargeable |
| No | Yes | Can't be set | Non-Chargeable | Billing on a time actual: Not available </br>Billing type on an expense actual: Non-chargeable |
| Yes | No | Chargeable | Can't be set | Billing on a time actual: Chargeable </br>Billing type on an expense actual: Not available |
| Yes | No | Non-Chargeable | Can't be set | Billing on a time actual: Non-chargeable </br> Billing type on an expense actual: Not available |
