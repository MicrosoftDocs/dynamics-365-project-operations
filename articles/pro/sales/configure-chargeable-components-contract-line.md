---
title: Configure chargeable components of a project-based contract line - lite
description: This topic provides information about how to add chargeable components to contract lines in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/08/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Configure chargeable components of a project-based contract line - lite

_**Applies To:** Lite deployment - deal to proforma invoicing_

A project-based contract line has *included* components and *chargeable* components.

Included components are components that are subject to:

  - Billing method and customer splits
  - Not-to-exceed limits 
  - Invoice frequency settings defined on the project-based contract line

A subset of the included components can be marked as chargeable using the **Billing Type** field. The **Billing Type** field is an option-set that allows the following values in the context of a contract line:

  - Chargeable
  - Non-chargeable

Chargeable components can be defined on tasks, roles, and transaction categories.

Chargeability is defined on tasks for a project contract line and applies to all transaction classes included on the line. If the **Include Tasks** field on a contract line is blank or set to **Entire project**, the **Chargeable tasks** tab will not be available.

Chargeability defined on roles for a project contract line only applies to the **Time** transaction class. If the **Include Time** field on a contract line is set to **No**, the **Chargeable roles** tab will not be available.

Chargeability defined on transaction categories for a project contract line only applies to the **Expense** transaction class. If the **Include Expenses** field is set to **No**, the **Chargeable Categories** tab will not be available.

### Update a project task as chargeable or non-chargeable

A project task can be chargeable or non-chargeable on a specific contract line which makes the following setup possible:

If a project-based contract line includes **Time** and a certain task, **T1** is associated to it as chargeable. If there is a second contract line that includes **Expense**, you can associate the T1 task on the contract line as non-chargeable. The result is that all of the time recorded on the task is chargeable and all expenses are non-chargeable.

A task's billing type can be configured on the **Chargeable Tasks** tab of the contract line by updating the **Billing Type** field on the contract line tasks subgrid. Alternatively, you can update the **Billing Type** field on the subgrid of the task Billing setup of a project that shows the contract lines associated to a task.

### Update a role as chargeable or non-chargeable

A role can be chargeable or non-chargeable on a specific contract line.

A role's billing type can be configured on the **Chargeable Roles** tab of a contract line. To do this, update the **Billing Type** field on the **Chargeable Roles** subgrid.

### Update a transaction category as chargeable or non-chargeable

A transaction category can be chargeable or non-chargeable on a specific contract line.

A transaction's billing type can be configured on the **Chargeable Categories** tab of a project-based contract line. To do this, update the **Billing Type** field on the **Chargeable Categories** subgrid.

### Resolve chargeability

An estimate or actual created for time will only be considered chargeable if **Time** is included on the contract line, and if **Task** and **Role** are configured as chargeable on the contract line.

An estimate or actual created for expense is only considered chargeable if **Expense** is included on the contract line and if the **Task** and **Transaction** categories are configured as chargeable on the contract line.


| Includes Time | Includes Expense | Includes Tasks | Role           | Category       | Task                                                                                                      |
|---------------|------------------|----------------|----------------|----------------|-----------------------------------------------------------------------------------------------------------|
| Yes           | Yes              | Entire project | Chargeable     | Chargeable     | Billing on a Time actual: **Chargeable** </br> Billing type on Expense actual: **Chargeable**           |
| Yes           | Yes              | Selected tasks | Chargeable     | Chargeable     | Billing on a Time actual: **Chargeable** </br> Billing type on Expense actual: **Chargeable**           |
| Yes           | Yes              | Selected tasks | Non-chargeable | Chargeable     | Billing on a Time actual: **Non-chargeable** </br> Billing type on Expense actual: **Chargeable**       |
| Yes           | Yes              | Selected tasks | Chargeable     | Chargeable     | Billing on a Time actual: **Non-chargeable** </br> Billing type on Expense actual:   **Non-chargeable** |
| Yes           | Yes              | Selected tasks | Non-chargeable | Chargeable     | Billing on a Time actual: **Non-chargeable** </br> Billing type on Expense actual:   **Non-chargeable** |
| Yes           | Yes              | Selected tasks | Non-chargeable | Non-chargeable | Billing on a Time actual: **Non-chargeable** </br> Billing type on Expense actual:   **Non-chargeable** |
| No            | Yes              | Entire project | Can't be set   | Chargeable     | Billing on a Time actual: **Not available**</br>Billing type on Expense actual: **Chargeable**          |
| No            | Yes              | Entire project | Can't be set   | Non-chargeable | Billing on a Time actual: **Not available**</br> Billing type on Expense actual: **Non-chargeable**     |
| Yes           | No               | Entire project | Chargeable     | Can't be set   | Billing on a Time actual: **Chargeable** </br> Billing type on Expense actual: **Not available**        |
| Yes           | No               | Entire project | Non-chargeable | Can't be set   | Billing on a Time actual: **Non-chargeable** </br>Billing type on Expense actual: **Not   available**   |
