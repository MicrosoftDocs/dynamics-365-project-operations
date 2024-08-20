---
title: Create proforma project invoices with Billing hub
description: This article provides information about how to use Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 08/20/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Create proforma project invoices with Billing hub

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

The end-to-end process of invoice creation in Microsoft Dynamics 365 Project Operations is cumbersome, because it involves multiple clicks and navigation between different forms and views.

The purpose of the **Billing hub experience** is to provide a rich, consolidated view of contracts, contract lines, related actuals, and key invoicing insights **before invoice creation**, to help accountants and billing users **quickly** and **efficiently** create proforma invoices. By using the platform's out-of-box nested grid functionality, users can complete invoice creation from a single unified view and through a single click. Because users don't have to move between forms or views to validate data, the processing of invoices is faster.

## Create new invoices

To use Billing hub to create project proforma invoices, follow this step.

- In the left pane, go to **Sales** \> **Billing Hub**.

The default **Billing hub** view shows the list of active project contracts and contract lines in a nested grid.
The following information is available in the **Billing hub** view.

### Contract fields

| Field | Description |
|---|---| 
| Name | The name of the project contract. |
| Customer | The name of the primary customer on the contract. |
| Total Amount | The amount on the contract. This amount is also referred to as the *contract value*. |
| Spent Amount | The total amount that confirmed invoices consumed for the contract until date. |
| Ready to be invoiced | The total number of transactions that have a **Ready to invoice** billing status. |
| Available advances | The total number of advances that are available for use against an invoice for the related project contract. |
| Advances| The total number of advances or retainers that were created for the contract. |
| Products | The number of product-based lines on the contract. |

### Contract line fields

| Field | Description |
|---|---| 
| Name | The name of the project contract line. |
| Project | The name of the project that is associated with the contract line. |
| Customers| The number of customers on the contract. |
| Billing Method | The billing method on the related project contract line. |
| Milestones | All the invoiceable fixed price milestones that are available for the selected project contract line. |
| Time | The billing backlog for all unbilled sales actuals of the **time** transaction type for the selected project contract line. |
| Material | The billing backlog for all unbilled sales actuals of the **material** transaction type for the selected project contract line. |
| Expense | The billing backlog for all unbilled sales actuals of the **expense** transaction type for the selected project contract line. |
| Fee | The billing backlog for all unbilled sales actuals of the **fee** transaction type for the selected project contract line. |
| Invoiceable backlog | The billing backlog that includes all invoiceable transactions for the project contract line. |
| Spent Amount | The previously billed backlog that includes all transactions that are already invoiced for the project contract line. |

### Update totals on contract and contract line fields

At any point during the invoicing process, use the **Update Totals** action to update all the calculated fields on the contract and contract lines. For newly added project contracts, amount values are initially **0** (zero).

To update totals on contract and contract line fields, follow these steps.

1. Select one or more project contracts.
1. On the Action Pane, select **Update Totals**.

## Review or update the invoiceable backlog per contract line

The contract lines for each project contract provide a view of all associated actuals for time, expenses, materials, and fees. The invoiceable backlog provides a comprehensive list of actuals across all transaction types. Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as either ready or not ready to be invoiced.

To review or update the invoiceable backlog, follow these steps.

1. For a time and material project contract line that has approved time entries, for example, select the **Time** amount field. Alternatively, you can select the **Invoiceable backlog** amount field. A list of invoiceable time transactions that are specific to the project contract and contract line appears.
1. Select the transactions, and then update the billing status by selecting **Ready to invoice** or **Not ready to invoice** in the list of options for the subgrid.
1. On the **Billing hub** page, select **Update Totals**. All calculated fields on the contract and contract lines are updated so that they reflect the latest status.

### Take actions on transactions in the billing backlog

To take actions on transactions in the billing backlog, follow these steps.

1. Mark transactions as invoiceable.
1. Reevaluate the not-to-exceed status of transactions.
1. Correct entries by using journals.
1. For each contract line, create new invoices directly from the billing backlog by using the **Create invoice** functionality.
1. Add transactions to an existing invoice by using the **Add to invoice** functionality.

When you use the **Add to invoice** functionality, you can expect the following behavior:

- If a single draft invoice exists for the project contract and project contract customer, the transaction is added to the invoice.
- If more than one draft invoice exists for the project contract and project contract customer, the transaction is added to the most recently created draft invoice.
- If no draft invoices exist, a new invoice is created that has the selected transactions. This behavior is similar to the behavior for the **Create invoice** functionality.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
