---
title: Configure chargeable components on project quote lines
description: This article provides information about setting up chargeable and nonchargeable components on a project-based quote line.
author: poojafandan
ms.author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure chargeable components on project quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

A project-based quote line has the concept of *included* components and *chargeable* components.

Included components are subject to:

  - Billing method and customer splits
  - Not-to-exceed limits 
  - Invoice frequency settings defined on the project-based quote line

A subset of the included components can be marked as chargeable using the **Billing Type** field. The **Billing Type** field is an option-set that allows the following values in the context of a quote line:

  - Chargeable
  - Nonchargeable

Chargeable components can be defined on tasks, roles, and transaction categories.

Chargeability is defined on the tasks for a quote line and applies to all transaction classes included on that line. If the **Include Tasks** field is set to **Entire project** or left blank, the **Chargeable Tasks** tab isn't available.

Chargeability is defined on roles for a quote line and only applies to the **Time** transaction class. If the field, **Include Time** is set to **No** on a project quote line, the **Chargeable Roles** tab isn't available.

Chargeability is defined on transaction categories for a  quote line and only applies to the **Expense** transaction class. If the field, **Include Expenses** is set to **No** on a project quote line, the **Chargeable Categories** tab isn't available.

### Update a project task to be chargeable or nonchargeable

A project task can be chargeable or nonchargeable in the context of a specific project-based quote line, which makes the following setup possible.

If a project-based quote line includes **Time** and the task **T1**, the task is associated to the quote line as chargeable. If there's a second quote line that includes **Expenses**, you can associate the **T1** task on the quote line as nonchargeable. The result is that all time recorded on the task is chargeable and all expenses recorded on the task are nonchargeable.

You can configure a task's billing type on the **Chargeable Tasks** tab of a project-based quote line by updating the **Billing Type** field on the **Quote Line Tasks** subgrid. Alternatively, you can update the billing type for a project task in the **Billing Type** field on the subgrid on the task billing setup of a project that shows the quote lines associated to a task.

### Update a role to be chargeable or nonchargeable

A role can be chargeable or nonchargeable in the context of a specific project-based quote line.

You can configure a role's billing type on the **Chargeable Roles** tab of a quote line by updating the **Billing Type** field on the **Chargeable Roles** subgrid.

### Update a transaction category to be chargeable or nonchargeable

A transaction category can be chargeable or nonchargeable on a specific quote line.

You can configure a transaction's billing type on the **Chargeable Categories** tab of a quote line by updating the **Billing Type** field on the **Chargeable Categories** subgrid.

### Resolve chargeability
An estimate or actual created for time is only considered chargeable if:

   - **Time** is included on the quote line.
   - **Role** is configured as chargeable on the quote line. If the role isn't mentioned as chargeable at quote line, set it as chargeable in the master.

   - **Included Tasks** is set to **Selected tasks** on the quote line. 

If these three conditions are true, the **Task** is also configured as chargeable. 

An estimate or actual created for expense is only considered chargeable if: 

   - **Expense** is included on the quote line.
   - **Transaction category** is configured as chargeable on the quote line. If the transaction category isn't mentioned as chargeable at quote line, set it as chargeable in the master.

   - **Included Tasks** is set to **Selected tasks** on the quote line.

If these three conditions are true, the **Task** is also configured as chargeable. 

An estimate or actual created for material is only considered chargeable if:

   - **Materials** is included on the quote line.
   - **Included Tasks** is set to **Selected tasks** on the quote line.

If these two conditions are true, the **Task** should also be configured as chargeable. 


| Includes Time | Includes Expense | Includes Materials | Included Tasks | Role | Category | Task | Chargeability impact |
|---|---|---|---|---|---|---|---|
| Yes | Yes | Yes | Entire Project | Chargeable | Chargeable | Can't be set | Billing on a time actual: Chargeable<br>Billing type on expense actual: Chargeable<br>Billing type on material actual: Chargeable |
| Yes | Yes | Yes | Selected tasks only | Chargeable | Chargeable | Chargeable | Billing on a time actual: Chargeable<br>Billing type on expense actual: Chargeable<br>Billing type on material actual: Chargeable |
| Yes | Yes | Yes | Selected tasks only | **Non - Chargeable** | Chargeable | Chargeable | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: Chargeable<br>Billing type on material actual: Chargeable |
| Yes | Yes | Yes | Selected tasks only | Chargeable | Chargeable | **Nonchargeable** | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: **Nonchargeable**<br>Billing type on material actual: **Nonchargeable** |
| Yes | Yes | Yes | Selected tasks only | **Nonchargeable** | Chargeable | **Nonchargeable** | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: **Nonchargeable**<br>Billing type on material actual: **Nonchargeable** |
| Yes | Yes | Yes | Selected tasks only | **Nonchargeable** | **Nonchargeable** | Chargeable | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: **Nonchargeable**<br>Billing type on material actual: Chargeable |
| **No** | Yes | Yes | Entire Project | Can't be set | **Chargeable** | Can't be set | Billing on a time actual: **Not available**<br>Billing type on expense actual: Chargeable<br>Billing type on material actual: Chargeable |
| **No** | Yes | Yes | Entire Project | Can't be set | **Nonchargeable** | Can't be set | Billing on a time actual: **Not available**<br>Billing type on expense actual: **Nonchargeable**<br>Billing type on material actual: Chargeable |
| Yes | **No** | Yes | Entire Project | Chargeable | Can't be set | Can't be set | Billing on a time actual: Chargeable<br>Billing type on expense actual: **Not available**<br>Billing type on material actual: Chargeable |
| Yes | **No** | Yes | Entire Project | **Nonchargeable** | Can't be set | Can't be set | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: **Not available**<br>Billing type on material actual: Chargeable |
| Yes | Yes | **No** | Entire Project | Chargeable | Chargeable | Can't be set | Billing on a time actual: Chargeable<br>Billing type on expense actual: Chargeable<br>Billing type on material actual: **Not available** |
| Yes | Yes | **No** | Entire Project | **Nonchargeable** | **Nonchargeable** | Can't be set | Billing on a time actual: **Nonchargeable**<br>Billing type on expense actual: **Nonchargeable**<br>Billing type on material actual: **Not available** |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
