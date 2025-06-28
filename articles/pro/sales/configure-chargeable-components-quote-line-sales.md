---
title: Configure chargeable components on project quote lines
description: This article provides information about setting up chargeable and nonchargeable components on a project-based quote line.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure chargeable components on project quote lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing, Project Operations Integrated with ERP_

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

A task's billing type can be configured on the **Chargeable Tasks** tab of a project-based quote line by updating the **Billing Type** field on the **Quote Line Tasks** subgrid. Alternatively, you can update the billing type for a project task in the **Billing Type** field on the subgrid on the task billing setup of a project that shows the quote lines associated to a task.

### Update a role to be chargeable or nonchargeable

A role can be chargeable or nonchargeable in the context of a specific project-based quote line.

A role's billing type can be configured on the **Chargeable Roles** tab of a quote line by updating the **Billing Type** field on the **Chargeable Roles** subgrid.

### Update a transaction category to be chargeable or nonchargeable

A transaction category can be chargeable or nonchargeable on a specific quote line.

A transaction's billing type can be configured on the **Chargeable Categories** tab of a quote line by updating the **Billing Type** field on the **Chargeable Categories** subgrid.

### Resolve chargeability
An estimate or actual created for time is only considered chargeable if:

   - **Time** is included on the quote line.
   - **Role** is configured as chargeable on the quote line. If the role isn't mentioned as chargeable at quote line, then it must be set up as chargeable in the master.

   - **Included Tasks** is set to **Selected tasks** on the quote line. 

If these three things are true, the **Task** is also configured as chargeable. 

An estimate or actual created for expense is only considered chargeable if: 

   - **Expense** is included on the quote line.
   - **Transaction category** is configured as chargeable on the quote line. If the transaction category isn't mentioned as chargeable at quote line, then it must be set up as chargeable in the master.

   - **Included Tasks** is set to **Selected tasks** on the quote line.

If these three things are true, the **Task** is also configured as chargeable. 

An estimate or actual created for material is only considered chargeable if:

   - **Materials** is included on the quote line.
   - **Included Tasks** is set to **Selected tasks** on the quote line.

If these two things are true, the **Task** should also be configured as chargeable. 


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
                    Billing on a time actual: Chargeable
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
                    Chargeable
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
