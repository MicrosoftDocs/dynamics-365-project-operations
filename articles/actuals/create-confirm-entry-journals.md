---
title: Create and confirm Entry journals
description: This article provides information about how to create and confirm Entry journals in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.author: nshrivastava
ms.date: 01/23/2026
ms.topic: how-to
mscustom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create and confirm Entry journals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core_

Use Entry journals to record actuals directly in Microsoft Dynamics 365 Project Operations. When you use Entry journals, you don't have to enter Time, Expense, and Material usage logs in Project Operations.

A single Entry journal lets you create multiple journal lines. When you confirm the journal, an Entry journal line records the actual for the following details:

- The cost or revenue, depending on the transaction type that you select.
- The selected class of transaction. The available classes are **Time**, **Expense**, **Material**, **Retainer**, **Milestone**, and **Tax**.
- The project and task that you select on the journal line.

Use Entry journals to create actuals outside of the standard process of submitting and approving a time, material, and expense entry. Use it for situations where creating individual entries is infeasible, including data migration.

Follow these steps to create an Entry journal in Project Operations.

1. Go to **Sales** \> **Transactions** \> **Journals**.
1. On the **Entry journals** list, on the Action Pane, select **New** to create a journal.
1. On the **New journal** page, in the **Description** field, enter a description of the journal.
1. Make sure that the **Journal type** field is set to **Entry**, and then select **Save**. After you save the new Entry journal, a **Journal lines** tab appears on the journal page.
1. On the **Journal lines** tab, on the toolbar above the grid, select **New** to create an Entry journal line.
1. In the **Quick create** dialog box for creating an Entry journal line, set the fields as described in the following table.

    | Field | Description | Functional impact |
    | --- | --- | --- |
    | Transaction Class | Classify the journal line into one of the six transaction classes: **Time**, **Expense**, **Material**, **Retainer**, **Milestone**, or **Tax**. | <p>The **Tax** transaction class is deprecated in Project Operations.</p><p>If you create a **Tax** transaction class, invoicing doesn't process it and it isn't included in cost or revenue calculations. **Milestone** is a revenue-only transaction class.</p><p>The **Retainer** transaction class represents an advance that a customer sends. Always create it as a pair of billed sales and unbilled sales journal lines.</p> |
    | Transaction Type | <p>Use the **Cost**, **Interorg Sales**, and **Resourcing unit cost** transaction types to record cost.</p><p>Use the **Unbilled Sales** and **Billed Sales** transaction types to record revenue.</p> | <p>The **Retainer** transaction class works only with the **Unbilled Sales** and **Billed Sales** transaction types.</p><p>The **Milestone** transaction class works only with the **Billed Sales** transaction type.</p><p>The **Interorg Sales** and **Resourcing unit cost** transaction types apply only to the **Time** transaction class. In addition, they're available on Entry journals only in the Project Operations Core scenario. They're not available when Project Operations is deployed in the Project Operations Integrated with ERP scenarios.</p> |
    | Select Product | When you select the **Material** transaction class, specify whether the material transaction that you're creating the journal line for is an existing product or a write-in product. | If you select **Write-in product**, enter a name for the product. |
    | Product | A reference to the product from the catalog. | |
    | Description | A description of the journal line to help make it easy to identify. | For unbilled sales journal lines, the value is used as the description when the invoice line details are created. |
    | External description | A description of the journal line that you can use for sharing with external stakeholders. | For unbilled sales journal lines, the value is used as the external description when the invoice line details are created. It can also appear on the invoice that is sent to the customer. |
    | Billing Type | A value that indicates whether the journal line is counted as a chargeable, complimentary, or nonchargeable component on the project. | In a typical flow, the billing type is derived from the agreed-on terms that are set up on the contract. However, when you record a journal line, you can enter a value in this field. |
    | Document date | Use a date when the transaction occurred. | |
    | Start Date | Use the date when the transaction occurred. | This field is used for comparison with the date of invoice creation for transactions of the **Unbilled Sales** type. This comparison helps you decide whether the transaction is future-dated or past-dated. Only past-dated transactions are added to the invoice. |
    | End Date | Use the date when the transaction occurred. | |
    | Accounting Date | Use the date when the accounting impact is recorded. | |
    | Contract line customer | By default, if the contract line has only one customer, this field is set to the customer on the contract line when the journal line is saved. If the contract line has multiple customers, select the correct customer on the contract line. | If the system can't determine the contract line customer on the journal line, and if it's blank on the actual of the **Unbilled Sales** type that is created from the journal line, the actual isn't invoiced. |
    | Project | Select the project to record the actual on. | Based on the selected project, transaction class, and task, the system tries to determine the contract, contract line, and contract line customer. |
    | Task | Select the task to record the actual on. | If you associated tasks with contract lines during contract setup, the system uses the selected task, together with a project and transaction class, to determine the contract, contract line, and contract line customer. |
    | Transaction Category | Select the transaction category to record the actual on. | For expenses, the selected transaction category determines the default price that is entered on the journal line when saved. |
    | Role | This field is relevant to Time journal lines. Select the role of the resource who spent time on the project and task. | For Time journal lines, if you use the out-of-box configuration for the entry of default resource costs and bill rates, the selected role is used together with the resourcing unit to determine the default price that is entered on the journal line when saved. If you use a custom configuration for the entry of default prices, review that configuration to determine whether the **Role** field is used to enter default price values. |
    | Subcontract | If the journal line represents subcontracted capacity, or subcontracted expenses or materials, select the relevant subcontract. | When you record Cost journal lines, the selected subcontract determines the price list that is used to enter the default unit cost. |
    | Subcontract line | If the journal line represents subcontracted capacity, or subcontracted expenses or materials, select the relevant subcontract line. | When you record Cost journal lines, the selected subcontract line ensures that the available capacity calculations on the subcontract line are done correctly. |
    | Amount Method | By default, this field is set to **Multiply Quantity By Price**. When you use this method, the amount is calculated as *Quantity* × *Price*. The other supported method is **Fixed Price**. When you use this method, the price is set to the amount, and the quantity isn't used in the calculation. | |
    | Unit Schedule and Unit | Together, the unit schedule and unit identify the unit of the quantity. | The combination of the unit and the transaction category is used to enter default prices for expenses. In the default configuration of Project Operations, the combination of the unit, role, and resourcing unit is used to enter default prices for time. If you have a custom configuration for the entry of default prices, it's used together with the unit. The combination of the product and the unit is used to enter default prices for materials. |
    | Quantity | Enter the quantity. | |
    | Price | If you leave the price blank when you create the journal line, the relevant values are used to enter the default prices, depending on the transaction class. If you enter a price when you create the journal line, that price is used. | |
    | Tax | Enter any tax amount. | Depending on the tax amount that you enter, the extended amount is calculated as *Amount* + *Tax*. |

## Confirm an Entry journal

After you enter all the journal lines in an Entry journal, you can confirm the journal. This process records each journal line as actuals on the appropriate projects.

After you confirm a journal, you can no longer edit it or any of its lines.

## Actuals created by Entry journal confirmation

A few key differences exist between actuals created by Entry journal confirmation and actuals created during approval of Time, Expense, and Material usage logs and invoice confirmation in Project Operations:

- Entry journals don't use transaction connections to link the cost actual to the unbilled sales actual. The actuals that are created when you approve Time, Expense, and Material usage logs always use transaction connections to link the cost and unbilled sales actuals.
- Entry journals don't use transaction origins to link the cost actual and the unbilled sales actuals to any originating record. The actuals that are created when you approve Time, Expense, and Material usage logs always use transaction origins to link the cost and unbilled sales actuals to the originating time entry.
- When you invoice unbilled sales actuals that are created by Entry journal confirmation, the billed sales actuals that are created during invoice confirmation are linked to the unbilled sales actuals, in a similar manner to the unbilled sales actuals that are created when you approve Time, Expense, and Material usage logs.
- Entry journal lines that you create for time that is entered by inter-organizational resources don't cause actuals of the **Resourcing unit cost** and **Interorg Sales** types to be automatically created. You must manually create these actuals. This behavior differs from the behavior for time entries recorded by inter-organizational resources. In that case, when time is approved, the application automatically creates actuals of the **Cost** type on the project and actuals of the **Resourcing unit cost** and **Interorg Sales** types on the employee's owning division. It then uses transaction connections to link those actuals together and transaction origins to link them to the originating time entry.
- When you confirm Entry journals, they create actuals. However, you can't use Correction journals to correct those actuals. This behavior differs from the behavior for actuals that are created when you approve Time, Expense, and Material usage logs. In that case, the application lets you use Correction journals to correct the actuals to fix any errors, provided those actuals aren't yet invoiced. If they're already invoiced, you can still correct an actual if you process a full credit of that actual to the customer.

> [!NOTE]
> By default, Entry journals don't enforce strict defaulting rules. Therefore, use them as little as possible, and exercise caution and care to ensure that you don't create corrupted financial data in your system. Whenever you can, use Time, Expense, and Material usage logs, the milestone and retainer setup on project contracts, and the project invoice confirmation process instead of Entry journals to create actuals.
> 
> To enforce rules for the journal lines, enable the **Journal line improvements** feature. For more information, see [Journal line improvements](journal-line-improvements.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
