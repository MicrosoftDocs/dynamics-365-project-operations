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
| Invoice Schedule Type | Indicates whether the fixed price contract line will be billed as a regular milestone or a progress based milestone. |
| Milestones | All the invoiceable fixed price milestones that are available for the selected project contract line. |
| Time | The billing backlog for all unbilled sales actuals of the **time** transaction type for the selected project contract line. |
| Material | The billing backlog for all unbilled sales actuals of the **material** transaction type for the selected project contract line. |
| Expense | The billing backlog for all unbilled sales actuals of the **expense** transaction type for the selected project contract line. |
| Fee | The billing backlog for all unbilled sales actuals of the **fee** transaction type for the selected project contract line. |
| Invoiceable backlog | The billing backlog that includes all invoiceable transactions for the project contract line. |
| Spent Amount | The previously billed backlog that includes all transactions that are already invoiced for the project contract line. |

> [!IMPORTANT]
> At any point during the invoicing process, use the **Update Totals** action on the Billing hub form, to update all the calculated fields on the contract and contract lines. For newly added project contracts, amount values are initially **0** (zero).

## Update the invoiceable backlog per contract line

The contract lines for each project contract provide a view of all associated actuals for time, expenses, materials, and fees. The invoiceable backlog provides a comprehensive list of actuals across all transaction types. Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as either ready or not ready to be invoiced.

To review or update the invoiceable backlog, follow these steps.

1. For a time and material project contract line that has approved time entries, for example, select the **Time** amount field. Alternatively, you can select the **Invoiceable backlog** amount field. A list of invoiceable time transactions that are specific to the project contract and contract line appears.
1. Select the transactions, and then update the billing status by selecting **Ready to invoice** or **Not ready to invoice** in the list of options for the subgrid.
1. On the **Billing hub** page, select **Update Totals**. All calculated fields on the contract and contract lines are updated so that they reflect the latest status.

   
## Possible billing actions on transactions in the Invoiceable backlog

For each available contract line, when the billing backlog amount is not zero, the following actions are possible.

1. Mark transactions as invoiceable or not invoiceable using **"Ready to Invoice"** or **"Not ready to invoice"** options.
1. **Reevaluate not-to-exceed** status of transactions.
1. **Correct entries** by using journals.
1. Directly **create new invoices** from the billing backlog by using the **Create invoice** functionality.
1. Add transactions to an existing invoice by using the **Add to invoice** functionality.

### **Create invoice** feature
- When the **Create invoice** on the Billing hub form is used, a new invoice is created with all transactions that are in **ready to invoice** state across all project contract lines for the selected contract(s).
- When the **Create invoice** on the billing backlog for Time, material, expense, fee, or milestones is used, an invoice is created with only the selected transactions in the backlog. 

### **Add to invoice** feature
When you use the **Add to invoice** functionality, you can expect the following behavior:

- If a single draft invoice exists for the project contract and project contract customer, the transaction is added to the invoice.
- If more than one draft invoice exists for the project contract and project contract customer, the transaction is added to the most recently created draft invoice.
- If no draft invoices exist, a new invoice is created with the selected transactions. This behavior is similar to the behavior for the **Create invoice** functionality.

### Update totals on contract and contract line fields

To update totals on contract and contract line fields, follow these steps.

1. Select one or more project contracts.
1. On the Action Pane, select **Update Totals**.

### Create invoices with Progress based milestones

Billing hub supports the ability to generate invoices for progress billed milestones. Progress based billing provides flexibility in billing and allows customers to realize revenue in regular increments as work towards the milestone is completed. 
Progress based milestones are indicated on the contract lines with **invoice schedule type** field set to **Progress based**. 

The following fields are available on the milestone billing backlog for progress based milestones.

On the progress based Milestone Header-

| Field | Description |
|---|---| 
| Name | The name of the milestone. |
| Task | Project task that the milestone is associated with. |
| Amount | Total milestone amount to be billed . |
| Next invoice % | % of the total amount including tax that should be invoiced on the next invoice for this progress-based invoice schedule component. |
| Next invoice amount | Amount that should be on the next invoice for this progress-based invoice schedule component. |
| Next invoice status | Status of the next invoice for this progress-based invoice schedule component. |
| Invoiced to date | Amount that has already been invoiced for this progress-based invoice schedule component. |
| % Invoiced to date | Percent of the total amount including tax that has already been invoiced for this progress-based invoice schedule component. |
| Remaining amount | Amount available to be spent against the not-to-exceed limit. |
| Tax |Tax amount for this transaction. |
| Not-to-exceed status | Status of the transaction evaluated against NTE limits set on the project contract, or project contract customer. |

On the progress based milestone line-

| Field | Description |
|---|---| 
| Project Contract line customer | Name of the customer who will be invoiced for this milestone transaction |
| Amount | A portion of the total amount on the corresponding milestone header, that has been billed or will be billed to the project contract customer, depdending on the invoice status |
| Date | Invoicing date for the milestone |
| Invoice Status | Current invoicing status of the progress based billing milestone |

To create an invoice for a progress based milestone(s), follow the steps below.
On all milestones that need to be invoiced,
1. Update the Next invoice %
1. Update the Next invoice status to "Ready for invoicing" using **Next invoice status** field or using **Ready to invoice** grid action on the milestone header.
1. Deselect the milestone header row(s)
1. **Refresh** grid

> [!IMPORTANT]
> **Updating the status of this milestone header to "ready for invoicing"  and refreshing the grid, will create a split of 2 milestone lines under this milestone header.**

To create an invoice with the selected progress based milestones, follow the steps below.
1. Select the milestone header 
1. Choose between the grid actions to either "Create invoice" or "Add to invoice"

For example, consider Amount on the milestone header is $1000 , Next invoice % is 20% , then Next invoice amount is $200. 
   
Update the status of this milestone header to "ready for invoicing"  and refresh the grid. This will create a split of 2 milestone lines under this milestone header.
   
  1. $200 amount with "Ready for invoicing" status
  2. $800 amount with "Not ready for invoicing" status
   
Selecting the milestone header which has $200 in "ready for invoicing" state and selecting "Create invoice" creates a new invoice with the progress based milestone for $200 amount.
On confirming the invoice with this milestone, the invoice status of the milestone line in $200 changes to "Customer invoice posted" . 
You will now be able to create a new progress based milestone for , either the remaining amount of $800 or another 20% , i.e. $200. 
   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
