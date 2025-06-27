---
title: Configure chargeable components of a project contract line 
description: This article provides information about how to add chargeable components to contract lines in Project Operations.
author: rumant
ms.date: 12/03/2022
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Configure chargeable components of a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing, Project Operations Integrated with ERP_

A project contract line has *included* components and *chargeable* components.

Included components are components that are subject to:

  - Billing method and customer splits
  - Not-to-exceed limits 
  - Invoice frequency settings defined on the project-based contract line

A subset of the included components can be marked as chargeable using the **Billing Type** field. The **Billing Type** field is an option-set that allows the following values in the context of a contract line:

  - Chargeable
  - Nonchargeable

Chargeable components can be defined on tasks, roles, and transaction categories.

Chargeability is defined on tasks for a project contract line and applies to all transaction classes included on the line. If the **Include Tasks** field on a contract line is blank or set to **Entire project**, the **Chargeable tasks** tab isn't available.

Chargeability defined on roles for a project contract line only applies to the **Time** transaction class. If the **Include Time** field on a contract line is set to **No**, the **Chargeable roles** tab isn't available.

Chargeability defined on transaction categories for a project contract line only applies to the **Expense** transaction class. If the **Include Expenses** field is set to **No**, the **Chargeable Categories** tab isn't available.

### Update a project task as chargeable or nonchargeable

A project task can be chargeable or nonchargeable on a specific contract line, which makes the following setup possible:

If a project-based contract line includes **Time** and a certain task, **T1** is associated to it as chargeable. If there's a second contract line that includes **Expense**, you can associate the T1 task on the contract line as nonchargeable. The result is that all of the time recorded on the task is chargeable and all expenses are nonchargeable.

A task's billing type can be configured on the **Chargeable Tasks** tab of the contract line by updating the **Billing Type** field on the contract line tasks subgrid. Alternatively, you can update the **Billing Type** field on the subgrid of the task Billing setup of a project that shows the contract lines associated to a task.

### Update a role as chargeable or nonchargeable

A role can be chargeable or nonchargeable on a specific contract line.

A role's billing type can be configured on the **Chargeable Roles** tab of a contract line. To configure the billing type, update the **Billing Type** field on the **Chargeable Roles** subgrid.

### Update a transaction category as chargeable or nonchargeable

A transaction category can be chargeable or nonchargeable on a specific contract line.

A transaction's billing type can be configured on the **Chargeable Categories** tab of a project-based contract line. To configure the billing type, update the **Billing Type** field on the **Chargeable Categories** subgrid.

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

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="70" valign="top">
                <p>
                    <strong>Includes Time</strong>
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    <strong>Includes Expense</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    <strong>Includes Materials</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    <strong>Included Tasks</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Role</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    <strong>Category</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Task</strong>
                    <strong></strong>
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    <strong>Chargeability impact</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Chargeable</strong>
                </p>
                <p>
                    Billing type on expense actual: <strong>Chargeable</strong>
                </p>
                <p>
                    Billing type on material actual: <strong>Chargeable</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Chargeable</strong>
                </p>
                <p>
                    Billing type on expense actual: <strong>Chargeable</strong>
                </p>
                <p>
                    Billing type on material actual: <strong>Chargeable</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Non - Chargeable</strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable</strong>
                </p>
                <p>
                    Billing type on expense actual: Chargeable
                </p>
                <p>
                    Billing type on material actual: Chargeable
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable</strong>
                </p>
                <p>
Billing type on expense actual: <strong>Nonchargeable</strong>
                </p>
                <p>
Billing type on material actual: <strong>Nonchargeable</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable</strong>
                </p>
                <p>
Billing type on expense actual: <strong>Nonchargeable</strong>
                </p>
                <p>
Billing type on material actual: <strong> Nonchargeable</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable</strong>
                </p>
                <p>
Billing type on expense actual: <strong> Nonchargeable</strong>
                </p>
                <p>
                    Billing type on material actual: Chargeable
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    <strong>Chargeable</strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Not available</strong>
                </p>
                <p>
                    Billing type on expense actual: Chargeable
                </p>
                <p>
                    Billing type on material actual: Chargeable
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Not available</strong>
                </p>
                <p>
Billing type on expense actual: <strong> Nonchargeable</strong>
                </p>
                <p>
Billing type on material actual: Chargeable 
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: Chargeable
                </p>
                <p>
                    Billing type on expense actual:<strong> Not available</strong>
                </p>
                <p>
Billing type on material actual: Chargeable
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable </strong>
                </p>
                <p>
Billing type on expense actual:<strong> Not available</strong>
                </p>
                <p>
Billing type on material actual: Chargeable 
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    Chargeable
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: Chargeable
                </p>
                <p>
                    Billing type on expense actual: Chargeable
                </p>
                <p>
Billing type on material actual: <strong> Not available</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="70" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="78" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="63" valign="top">
                <p>
                    <strong>No</strong>
                </p>
            </td>
            <td width="75" valign="top">
                <p>
                    Entire Project
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="70" valign="top">
                <p>
                    <strong>Nonchargeable</strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    Can't be set
                </p>
            </td>
            <td width="350" valign="top">
                <p>
                    Billing on a time actual: <strong>Nonchargeable </strong>
                </p>
                <p>
Billing type on expense actual:<strong> Nonchargeable </strong>
                </p>
                <p>
Billing type on material actual:<strong> Not available</strong>
                </p>
            </td>
        </tr>
    </tbody>
</table>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
