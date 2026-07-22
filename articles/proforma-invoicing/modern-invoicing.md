---
title: Manage a proforma project invoice with modern invoice form
description:  This article explains how to work with proforma project invoices.
author: nshrivastava
ms.author: nshrivastava
ms.date: 07/22/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Improve invoice usability with modern invoicing

[!INCLUDE [banner](../includes/banner.md)]

*Applies to:* Dynamics 365 Project Operations Core, Dynamics 365 Project Operations integrated with ERP

The modern invoicing experience in Dynamics 365 Project Operations provides a consolidated view of contracts, contract lines, and invoiceable transactions. It includes usability enhancements that streamline invoice management, editing, and validation. These enhancements reduce the need to select options, improve clarity, and align with real-world billing workflows.

This article describes the usability improvements, supported actions, and design principles that guide the modern invoicing experience.

## Business value

Project-based organizations often manage thousands of transactions per invoice cycle. These transactions include time, expense, product usage, and milestone-based billing. The modern invoicing experience helps:

- Reduce time spent navigating between forms and views.
- Improve accuracy by surfacing key financial metrics before invoice confirmation.
- Enable intuitive editing of invoice line details (ILDs) and support faster decision-making with contextual insights.

## Feature highlights

### Modern invoice header

The modern invoice header provides a better view of invoice details.

| Label | Description |
| --- | --- |
| Summary | Provides a high-level financial overview of the invoice. |
| Details | Shows details such as addresses for the invoice. |  
| Time & Material     | Captures transactions like time entries, expenses, and materials. You can edit billing type, quantity, price, and tax directly. You can now create time and material based ILDs directly from the grid rather than by having to navigate to the invoice line record.                                                              |
| Fixed Price         | Displays milestone and progress based billing tied to fixed price contracts so you can manage milestone readiness and chargeability.                                                                                                                                                                                     |
| Advance & Retainers | Separates applied versus unapplied advances for better financial tracking and supports correction logic and backend validation for adjustments.                                                                                                                                                                                                                                   |
| Product             | Handles product-based billing lines.                                                                                                                                                                                                                                                                                                                                           |

### Bulk edit functionality

Bulk edit functionality is a usability enhancement in Project Operations' modern invoicing experience. It supports selecting multiple Invoice Line Details (ILDs) - which represent individual billable items such as time entries, expenses, products, or milestones - and updating their values in one action, rather than editing each line individually.

### How it works

- Selection: Select several ILDs at once from the invoice grid or subgrid.
- Editing: Once selected, apply changes (such as updating billing type, quantity, price, or tax) to all chosen ILDs in a single step.

### Editable invoice line details

Depending on the transaction type, you can edit:

- Time & Material: Billing type, quantity, price, tax.
- Fixed Price: Chargeability, price, tax.
- Products: Tax only.
- Applied Advances: Extended amount.
- Regular Advances: Not editable.

### Benefits

- Efficiency: This functionality reduces the number of select and repetitive actions, especially useful for invoices with many line items.
- Consistency: Bulk editing helps ensure that similar items are updated uniformly, minimizing errors and improving accuracy.

### Transaction insights

The system now provides a detailed view of transactions across the following sections:

### Pending Transactions

Shows all billable transactions that aren't yet added to the current invoice, including services performed, product deliveries, and other outstanding items awaiting invoicing. Select this section to review transaction details, select entries, and include them in the ongoing invoice. You can directly select time entries, milestones, and available and applied advances to include in the invoice from the Pending Transactions form. This streamlined process provides greater visibility and control to help ensure all relevant charges are captured, improve billing completeness, and support accurate financial reporting.

### Edited Transactions

Shows modifications to transactions that affect the invoice amount. These edits might include changes to quantities, prices, billing types, and taxes, that directly impact the invoice total. By surfacing these updates, you can maintain transparency and control over billing adjustments. Reviewing edited transactions ensures that you're aware of any post-creation changes, supports audit readiness, and enables accurate financial reconciliation.

> [!NOTE]
> For invoices created before enabling this feature, the system doesn't calculate pending transactions and edited transactions.

### Financial summary details

In addition to providing invoice details, the contract financial summary is shown to ensure that all necessary information is available. The financial summary details include:

- Contract Value: The total value defined in the contract.
- Billed Amount: The cumulative amount billed to date, excluding the current invoice.
- Current Invoice Amount: The amount being charged in this invoice.
- Remaining Amount: The balance left on the contract after subtracting the billed amount.
- NTE (Not-to-Exceed): The maximum allowable value under the contract.

### Set the accounting date on an invoice

To use this feature, turn on the **Enable Invoice Date Driven Accounting** feature flag.

When you confirm a project invoice, Project Operations creates the billed sales actuals for the invoiced transactions and posts the corresponding customer invoice in Finance and Operations. The **accounting date** on those postings determines the financial period in which the billed revenue is recognized.

By default, the accounting date is set to the date on which you confirm the invoice. With this capability, you can instead **define the accounting date directly on the invoice**, independent of each transaction's own transaction date and document date. This option gives billing and finance users control over the period in which billed revenue lands - without changing when the underlying work was recorded.

To set the accounting date on an invoice, follow these steps:

1. On the invoice header, in the **Accounting date** field, select the date that should drive the financial posting period for this invoice.
1. Review the invoice, and then select **Confirm**.

When you confirm the invoice, the accounting date you entered is applied to the billed sales actuals for that invoice and is used as the accounting date for the corresponding customer invoice posting in Finance and Operations.

The accounting date applies to billed sales actuals created when you confirm the invoice. It doesn't change the transaction date or document date of your actuals.

Tooltips and banners help you understand status changes and field refreshes.

## More information

[Proforma project invoices | Microsoft Learn](/dynamics365/project-operations/pro/proforma-invoicing/create-manual-proforma-invoice-sales)

[Manage a proforma project invoice | Microsoft Learn](/dynamics365/project-operations/pro/proforma-invoicing/manage-proforma-invoice-sales)

[Create proforma project invoices with Billing hub](/dynamics365/project-operations/proforma-invoicing/billing-hub)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
