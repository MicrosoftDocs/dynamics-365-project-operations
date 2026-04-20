---
title: Configure chargeable components of a project contract line 
description: Learn about how to add chargeable components to contract lines in Project Operations.
author: rumant
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Configure chargeable components of a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

A project contract line has **included** components and **chargeable** components.

Included components are components that are subject to:

- Billing method and customer splits
- Not-to-exceed limits
- Invoice frequency settings you define on the project-based contract line

You can mark a subset of the included components as chargeable by using the **Billing Type** field. The **Billing Type** field is an option set that offers the following values in the context of a contract line:

- Chargeable
- Nonchargeable

You can define chargeable components on tasks, roles, and transaction categories.

You define chargeability on tasks for a project contract line, and it applies to all transaction classes included on the line. If the **Include Tasks** field on a contract line is blank or set to **Entire project**, the **Chargeable tasks** tab isn't available.

Chargeability that you define on roles for a project contract line only applies to the **Time** transaction class. If the **Include Time** field on a contract line is set to **No**, the **Chargeable roles** tab isn't available.

Chargeability that you define on transaction categories for a project contract line only applies to the **Expense** transaction class. If the **Include Expenses** field is set to **No**, the **Chargeable Categories** tab isn't available.

### Update a project task as chargeable or nonchargeable

You can set a project task as chargeable or nonchargeable on a specific contract line, which makes the following setup possible:

If a project-based contract line includes **Time** and a certain task, you can associate the task to it as chargeable. If there's a second contract line that includes **Expense**, you can associate the task on the contract line as nonchargeable. The result is that all of the time recorded on the task is chargeable and all expenses are nonchargeable.

You can configure a task's billing type on the **Chargeable Tasks** tab of the contract line by updating the **Billing Type** field on the contract line tasks subgrid. Alternatively, you can update the **Billing Type** field on the subgrid of the task Billing setup of a project that shows the contract lines associated to a task.

### Update a role as chargeable or nonchargeable

You can set a role as chargeable or nonchargeable on a specific contract line.

You can configure a role's billing type on the **Chargeable Roles** tab of a contract line. To configure the billing type, update the **Billing Type** field on the **Chargeable Roles** subgrid.

### Update a transaction category as chargeable or nonchargeable

You can set a transaction category as chargeable or nonchargeable on a specific contract line.

You can configure a transaction's billing type on the **Chargeable Categories** tab of a project-based contract line. To configure the billing type, update the **Billing Type** field on the **Chargeable Categories** subgrid.

### Resolve chargeability

An estimate or actual created for time is only considered chargeable if:

- **Time** is included on the contract line.
- **Role** is configured as chargeable on the contract line. If the role isn't mentioned as chargeable at contract line, then it must be set up as chargeable in the master.
- **Included Tasks** is set to **Selected tasks** on the contract line.

 If these three things are true, the task is configured as chargeable.

An estimate or actual created for expense is only considered chargeable if:

- **Expense** is included on the contract line
- **Transaction category** is configured as chargeable on the contract line. If the transaction category isn't mentioned as chargeable at contract line, then it must be set up as chargeable in the master.
- **Included Tasks** is set to **Selected task** on the contract line
  
 If these three things are true, the **Task** is configured as chargeable.

An estimate or actual created for material is only considered chargeable if:

- **Materials** is included on the contract line
- **Included Tasks** is set to **Selected tasks** on the contract line

If these two things are true, the **Task** is configured as chargeable.

| Includes Time | Includes Expense | Includes Materials | Included Tasks | Role | Category | Task | Chargeability impact |
|---|---|---|---|---|---|---|---|
| Yes | Yes | Yes | Entire Project | Chargeable | Chargeable | Can't be set | Billing on a time actual: **Chargeable** <br> Billing type on expense actual: **Chargeable** <br> Billing type on material actual: **Chargeable** |
| Yes | Yes | Yes | Selected tasks only | Chargeable | Chargeable | Chargeable | Billing on a time actual: **Chargeable** <br> Billing type on expense actual: **Chargeable** <br> Billing type on material actual: **Chargeable** |
| Yes | Yes | Yes | Selected tasks only | **Non - Chargeable** | Chargeable | Chargeable | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: Chargeable <br> Billing type on material actual: Chargeable |
| Yes | Yes | Yes | Selected tasks only | Chargeable | Chargeable | **Nonchargeable** | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: **Nonchargeable** <br> Billing type on material actual: **Nonchargeable** |
| Yes | Yes | Yes | Selected tasks only | **Nonchargeable** | Chargeable | **Nonchargeable** | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: **Nonchargeable** <br> Billing type on material actual: **Nonchargeable** |
| Yes | Yes | Yes | Selected tasks only | **Nonchargeable** | **Nonchargeable** | Chargeable | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: **Nonchargeable** <br> Billing type on material actual: Chargeable |
| **No** | Yes | Yes | Entire Project | Can't be set | **Chargeable** | Can't be set | Billing on a time actual: **Not available** <br> Billing type on expense actual: Chargeable <br> Billing type on material actual: Chargeable |
| **No** | Yes | Yes | Entire Project | Can't be set | **Nonchargeable** | Can't be set | Billing on a time actual: **Not available** <br> Billing type on expense actual: **Nonchargeable** <br> Billing type on material actual: Chargeable |
| Yes | **No** | Yes | Entire Project | Chargeable | Can't be set | Can't be set | Billing on a time actual: Chargeable <br> Billing type on expense actual: **Not available** <br> Billing type on material actual: Chargeable |
| Yes | **No** | Yes | Entire Project | **Nonchargeable** | Can't be set | Can't be set | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: **Not available** <br> Billing type on material actual: Chargeable |
| Yes | Yes | **No** | Entire Project | Chargeable | Chargeable | Can't be set | Billing on a time actual: Chargeable <br> Billing type on expense actual: Chargeable <br> Billing type on material actual: **Not available** |
| Yes | Yes | **No** | Entire Project | **Nonchargeable** | **Nonchargeable** | Can't be set | Billing on a time actual: **Nonchargeable** <br> Billing type on expense actual: **Nonchargeable** <br> Billing type on material actual: **Not available** |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
