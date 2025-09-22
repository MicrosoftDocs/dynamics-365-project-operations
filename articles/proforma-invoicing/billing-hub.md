---
title: Create proforma project invoices with Billing hub
description: This article provides information about how to use Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 02/14/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Create proforma project invoices with Billing hub

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

The end-to-end process of invoice creation in Microsoft Dynamics 365 Project Operations is cumbersome, because it involves multiple clicks and navigation between different forms and views.

The purpose of the **Billing hub experience** is to provide a rich, consolidated view of contracts, contract lines, related actuals, and key invoicing insights **before invoice creation**, to help accountants and billing users **quickly** and **efficiently** create proforma invoices. When you use the platform's out-of-box nested grid functionality, users can complete invoice creation from a single unified view and through a single click. Because users don't have to move between forms or views to validate data, the processing of invoices is faster.

## Create new invoices

> [!NOTE]
> This process can be configured to be run in the background [using notifications](../../proforma-invoicing/long-running-jobs.md)

To use Billing hub to create project proforma invoices, follow this step.

- In the left pane, go to **Sales** \> **Billing Hub**.

The default **Billing hub** view shows the list of active project contracts and contract lines in a nested grid.

The following information is available in the **Billing hub** view. Learn how to customize **Billing hub** views in [Customizing Billing hub views](billing-hub-customization.md).

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
| Invoice Schedule Type | A value that indicates whether the fixed price contract line is billed as a regular milestone or a progress-based milestone. |
| Milestones | All the invoiceable fixed price milestones that are available for the selected project contract line. |
| Time | The billing backlog for all unbilled sales actuals of the **time** transaction type for the selected project contract line. |
| Material | The billing backlog for all unbilled sales actuals of the **material** transaction type for the selected project contract line. |
| Expense | The billing backlog for all unbilled sales actuals of the **expense** transaction type for the selected project contract line. |
| Fee | The billing backlog for all unbilled sales actuals of the **fee** transaction type for the selected project contract line. |
| Invoiceable backlog | The billing backlog that includes all invoiceable transactions for the project contract line. |
| Spent Amount | The previously billed backlog that includes all transactions that are already invoiced for the project contract line. |

> [!IMPORTANT]
> At any point during the invoicing process, use the **Update Totals** action on the **Billing hub** page to update all the calculated fields on the contract and contract lines. Because of the way that the platform handles roll-up fields, amount values for newly added project contracts are initially NULL. However, when you select **Update Totals**, the amounts are updated to the calculated values. 

## Update the invoiceable backlog per contract line

The contract lines for each project contract provide a view of all associated actuals for time, expenses, materials, and fees. The invoiceable backlog provides a comprehensive list of actuals across all transaction types. Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as either ready or not ready to be invoiced.

To review or update the invoiceable backlog, follow these steps.

1. For a time and material project contract line that has approved time entries, for example, select the **Time** amount field. Alternatively, you can select the **Invoiceable backlog** amount field. A list of invoiceable time transactions that are specific to the project contract and contract line appears.
1. Select the transactions, and then update the billing status by selecting **Ready to invoice** or **Not ready to invoice** in the list of options for the subgrid.
1. On the **Billing hub** page, select **Update Totals**. All calculated fields on the contract and contract lines are updated so that they reflect the latest status.

## Possible billing actions on transactions in the invoiceable backlog

For each available contract line that has a nonzero billing backlog amount, the following actions can be performed:

- **Mark transactions** as invoiceable by selecting **Ready to Invoice** or as not invoiceable by selecting **Not ready to invoice**.
- **Reevaluate the not-to-exceed status** of transactions.
- **Correct entries** by using journals.
- Directly **create new invoices** from the billing backlog by using the **Create invoice** functionality.
- **Add transactions** to an existing invoice by using the **Add to invoice** functionality.

### Create invoice feature

When the **Create invoice** functionality on the **Billing hub** page is used, the invoice that is created includes all transactions that are in a **Ready to invoice** state across all project contract lines for the selected contracts.

When the **Create invoice** functionality on the billing backlog for time, materials, expenses, fees, or milestones is used, the invoice that is created includes only the selected transactions in the backlog. 

### Add to invoice feature

When you use the **Add to invoice** functionality, you can expect the following behavior:

- If a single draft invoice exists for the project contract and project contract customer, the transaction is added to the invoice.
- If more than one draft invoice exists for the project contract and project contract customer, the transaction is added to the most recently created draft invoice.
- If no draft invoices exist, a new invoice is created that includes the selected transactions. This behavior is similar to the behavior for the **Create invoice** functionality.

### Update totals on contract and contract line fields

To update totals on contract and contract line fields, follow these steps.

1. Select one or more project contracts.
1. On the Action Pane, select **Update Totals**.

> [!NOTE]
> After the totals are updated, the grid is automatically updated to show the calculated amounts in the view.

### Create invoices with progress-based milestones

Billing hub supports the ability to generate invoices for milestones that are billed based on progress. Progress-based billing provides flexibility in billing and lets customers realize revenue in regular increments as work toward the milestone is completed.

You can easily identify progress-based milestones on contract lines because the **Invoice schedule type** field is set to **Progress based**.

> [!NOTE]
> The feature can be enabled at **Settings** \> **Parameters** \> **Feature control** \> **Progress billing updates**.

In the milestone billing backlog, the following fields are available for progress-based milestones.

#### Fields on the progress-based milestone header

| Field | Description |
|---|---| 
| Name | The name of the milestone. |
| Task | The project task that the milestone is associated with. |
| Amount | The total milestone amount to bill. |
| Next invoice % | The percentage of the total amount, including tax, that should be invoiced on the next invoice for this progress-based invoice schedule component. |
| Next invoice amount | The amount that should be invoiced on the next invoice for this progress-based invoice schedule component. |
| Next invoice status | The status of the next invoice for this progress-based invoice schedule component. |
| Invoiced to date | The amount that has already been invoiced for this progress-based invoice schedule component. |
| % Invoiced to date | The percentage of the total amount, including tax, that has already been invoiced for this progress-based invoice schedule component. |
| Remaining amount | The amount that is available to be spent against the not-to-exceed limit. |
| Tax | The tax amount for this transaction. |
| Not-to-exceed status | The status of this transaction, as evaluated against not-to-exceed limits that are set on the project contract or the project contract customer. |

#### Fields on the progress-based milestone line

| Field | Description |
|---|---| 
| Project Contract line customer | The name of the customer who is invoiced for this milestone transaction. |
| Project Contract line customer | The name of the customer who will be invoiced for this milestone transaction. |
| Amount | Of the total amount on the corresponding milestone header, the amount that has been billed or will be billed to the project contract customer, depending on the invoice status. |
| Date | The invoicing date for the milestone. |
| Invoice Status | The current invoicing status of the progress-based billing milestone. |

To create an invoice for progress-based milestones, follow these steps on all milestones that must be invoiced.

1. Update the **Next invoice %** value.
1. Update the **Next invoice status** value to **Ready for invoicing** either by using the **Next invoice status** field or by using the **Ready to invoice** grid action on the milestone header.
1. Clear the selection of the milestone header rows.

> [!NOTE]
> If you update the status of the milestone header to **Ready for invoicing** and then update the grid, you create a split of two milestone lines under the milestone header.

To create an invoice that includes the selected progress-based milestones, follow these steps.

1. Select the milestone header.
1. Select either the **Create invoice** grid action or the **Add to invoice** grid action.
1. Update the status of the milestone header to **Ready for invoicing**, and then update the grid. This update creates a split of two milestone lines under the milestone header.

For example, the **Amount** value on the milestone header is $1,000, the **Next invoice %** value is 20%, and the **Next invoice amount** value is $200. When you update the status of the milestone header to **Ready for invoicing** and then update the grid, the following split of two milestone lines is created under the milestone header:

- A $200 amount that has the **Ready for invoicing** status
- An $800 amount that has the **Not ready for invoicing** status

If you select the milestone header that has the $200 amount in the **Ready for invoicing** status, an you then select **Create invoice**, you create a new invoice that includes the progress-based milestone for the $200 amount.

After you confirm the invoice that includes this milestone, the invoice status of the milestone line that has the $200 amount is changed to **Customer invoice posted**.

You can now create a new progress-based milestone for either the remaining amount of $800 or another 20% (that is, another $200).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
