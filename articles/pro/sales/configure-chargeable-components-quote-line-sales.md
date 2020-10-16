---
title: Configure the chargeable components of a quote line
description: This topic provides information about setting up chargeable and non-chargeable components on a project-based quote line.
author: rumant
manager: Annbe
ms.date: 10/13/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Configure the chargeable components of a quote line

_**Applies To:** Lite deployment - deal to proforma invoicing_

A project-based quote line has the concept of *included* components and *chargeable* components.

Included components are subject to:

  - Billing method and customer splits
  - Not-to-exceed limits 
  - Invoice frequency settings defined on the project-based quote line

A subset of the included components can be marked as chargeable using the **Billing Type** field. The **Billing Type** field is an option-set that allows the following values in the context of a quote line:

  - Chargeable
  - Non-chargeable

Chargeable components can be defined on tasks, roles, and transaction categories.

Chargeability is defined on the tasks for a quote line and applies to all transaction classes included on that line. If the **Include Tasks** field is set to **Entire project** or left blank, the **Chargeable Tasks** tab isn't available.

Chargeability is defined on roles for a quote line and only applies to the **Time** transaction class. If the field, **Include Time** is set to **No** on a project quote line, the **Chargeable Roles** tab isn't available.

Chargeability is defined on transaction categories for a  quote line and only applies to the **Expense** transaction class. If the field, **Include Expenses** is set to **No** on a project quote line, the **Chargeable Categories** tab isn't available.

### Update a project task to be chargeable or non-chargeable

A project task can be chargeable or non-chargeable in the context of a specific project-based quote line, which makes the following setup possible:

If a project-based quote line includes **Time** and the task **T1**, the task is associated to the quote line as chargeable. If there is a second quote line that includes **Expenses**, you can associate the **T1** task on the quote line as non-chargeable. The result is that all time recorded on the task is chargeable and all expenses recorded on the task are non-chargeable.

A task's billing type can be configured on the **Chargeable Tasks** tab of a project-based quote line by updating the **Billing Type** field on the **Quote Line Tasks** sub-grid. Alternatively, you can update the billing type for a project task in the **Billing Type** field on the sub-grid on the task billing setup of a project that shows the quote lines associated to a task.

### Update a role to be chargeable or non-chargeable

A role can be chargeable or non-chargeable in the context of a specific project-based quote line.

A role's billing type can be configured on the **Chargeable Roles** tab of a quote line by updating the **Billing Type** field on the **Chargeable Roles** sub-grid.

### Update a transaction category to be chargeable or non-chargeable

A transaction category can be chargeable or non-chargeable on a specific quote line.

A transaction's billing type can be configured on the **Chargeable Categories** tab of a quote line by updating the **Billing Type** field on the **Chargeable Categories** sub-grid.

### Resolve chargeability
An estimate or actual created for time will only be considered chargeable if **Time** is included on the quote line, and if **Task** and **Role** are configured as chargeable on the quote line.

An estimate or actual created for expense will only be considered chargeable if **Expense** is included on the quote line, and if **Task** and **Transaction Category** are configured as chargeable on the quote line.

| Includes Time | Includes Expense | Included Tasks | Role | Category | Task | Billing |
| --- | --- | --- | --- | --- | --- | --- |
| Yes | Yes | Entire project | Chargeable | Chargeable | Can't be set | Billing on a time actual: Chargeable </br>Billing type on expense actual: Chargeable |
| Yes | Yes | Selected tasks only | Chargeable | Chargeable | Chargeable | Billing on a time actual: Chargeable</br>Billing type on expense actual: Chargeable |
| Yes | Yes | Selected tasks only | Non-chargeable | Chargeable | Chargeable | Billing on a time actual: Non-Chargeable</br>Billing type on expense actual: Chargeable |
| Yes | Yes | Selected tasks only | Chargeable | Chargeable | Non-Chargeable | Billing on a time actual: Non-Chargeable</br> Billing type on expense actual: Non-Chargeable |
| Yes | Yes | Selected tasks only | Non-Chargeable | Chargeable | Non- Chargeable | Billing on a time actual: Non-Chargeable</br> Billing type on expense actual: Non-Chargeable |
| Yes | Yes | Selected tasks only | Non-Chargeable | Non-Chargeable | Chargeable | Billing on a time actual: Non-Chargeable</br> Billing type on expense actual: Non-Chargeable |
| No | Yes | Entire project | Can't be set | Chargeable | Can't be set | Billing on a time actual: Not available </br>Billing type on expense actual: Chargeable |
| No | Yes | Entire project | Can't be set | Non-chargeable | Can't be set | Billing on a time actual: Not available </br>Billing type on expense actual: Non-chargeable |
| Yes | No | Entire project | Chargeable | Can't be set | Can't be set | Billing on a time actual: Chargeable</br>Billing type on expense actual: Not available |
| Yes | No | Entire project | Non-chargeable | Can't be set | Can't be set | Billing on a time actual: Non-chargeable </br>Billing type on expense actual: Not available |
