---
title: Create proforma project invoices with Billing hub
description: This article provides information about how to use Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 02/28/2024
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

The **Billing hub experience** aims to provide a rich, consolidated view of contracts, contract lines, related actuals, and key invoicing insights **before invoice creation**, to help accountants and billing users **quickly** and **efficiently** create proforma invoices. By using the platform's out-of-box nested grid functionality, users can complete invoice creation from a single unified view and through a single click. Because users don't have to move between forms or views to validate data, the processing of invoices is faster.

> [!NOTE]
> To use Billing hub, enable the feature at **Settings** \> **Parameters** \> **Feature control** \> **Billing hub**.
>
> After the feature becomes generally available, you'll be able to customize the Billing hub pages and views.

## Create new invoices

To begin to use Billing hub to create project proforma invoices, follow this step.

- In the left pane, go to **Sales** \> **Billing Hub**.

The default **Billing hub** view shows the list of active project contracts and contract lines in a nested grid.

### Update totals on contract and contract line fields

Initially, the values of amount fields might be shown as **0** (zero) for newly created project contracts. You can use the **Update Totals** button to view the latest values of amount fields in Billing hub.

To view the updated values of available amount fields, follow these steps.

1. Select the project contract.
1. On the Action Pane, select **Update Totals**.

### Review or update the invoiceable backlog

The contract lines for each project contract provide a view of all associated actuals for time, expenses, materials, and fees. The invoiceable backlog provides a comprehensive list of actuals across all transaction types. Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as either ready or not ready to invoice.

To review or update the invoiceable backlog, follow these steps.

1. For a Time and material project contract line that has approved time entries, for example, select the **Time** amount field. Alternatively, you can select the **Invoiceable backlog** amount field. A list of invoiceable time transactions that are specific to the project contract and contract line appears.
1. Select the transactions, and update the billing status by selecting **Ready to invoice** or **Not ready to invoice** in the list of options for the subgrid.
1. On the **Billing hub** page, select **Update Totals**. The **Ready to be invoiced** amount is updated.

The following information is available in the **Billing hub** view.

### Contract fields

| Field | Description |
|---|---| 
| Name | The name of the project contract. |
| Customer | The name of the primary customer on the contract. |
| Total Amount | The amount on the contract. This amount is also referred to as the *contract value*. |
| Ready to be invoiced | The total amount of transactions that have a **Ready to invoice** billing status. |
| Available advances | The total amount of advances that are available for use against an invoice for the related project contract. |
| Products | The number of product-based lines on the contract. |

### Contract line fields

| Field | Description |
|---|---| 
| Name | The name of the project contract line. |
| Project | The name of the project that's associated with the contract line. |
| Billing Method | The billing method on the related project contract line. |
| Milestones | All the invoiceable fixed price milestones that are available for the selected project contract line. |
| Time | The billing backlog for all unbilled sales actuals of the **time** transaction type for the selected project contract line. |
| Material | The billing backlog for all unbilled sales actuals of the **material** transaction type for the selected project contract line. |
| Expense | The billing backlog for all unbilled sales actuals of the **expense** transaction type for the selected project contract line. |
| Fee | The billing backlog for all unbilled sales actuals of the **fee** transaction type for the selected project contract line. |
| Invoiceable backlog | The billing backlog that includes all invoiceable transactions for the project contract line. |

> [!NOTE]
> Billing hub best supports scenarios where there is only one customer on the project contract or project contract line. Although it can be used in split billing scenarios, you might notice that the **Ready to invoice** amount doesn't differentiate the amounts that are split between the different customers that are included on the project contract or project contract line. For more information about split billing, see [Manage multiple customers on project-based contract lines](../sales/manage-multiple-customers-contract-line.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
