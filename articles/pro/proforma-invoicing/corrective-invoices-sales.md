---
title: Revised project invoices
description: This article provides information about how to create and confirm corrective invoices in Project Operations.
author: suvaidya    
ms.date: 09/05/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Revise project invoices

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

A confirmed project invoice can be revised to process changes or credits as negotiated with the customer and project manager.

To make edits to a confirmed invoice, open the confirmed invoice and select **Revise** (previously referred to as “Correct this invoice”). 
> [!NOTE] The invoice revision process has been significantly improved to include "Select transactions" capability so users can perform edits quickly resulting in improved user experience and productivity.   

Depending on the need to either edit only a few of the transactions or the entire invoice, use **Select transactions** or **Select all transactions**. 

**Select transactions** – Use this option to revise only specific transactions that were previously invoiced.

- Selecting this option opens a form with the list of invoice line details that have been previously invoiced. 
- Select the invoice line details for revision by setting the **revise** toggle to **yes**.
- Select the **create invoice** ribbon option to create a draft invoice with the selected transactions.

**Select all transactions** – Use this option to revise **ALL** the transactions on the confirmed invoice. 

> [!NOTE]
> Revise option is not available unless a project invoice is confirmed.

A new draft invoice is created from the confirmed invoice. 
- If **Select transactions** was used, selected invoice line details from the previously confirmed invoice are copied to the new draft. 
- If **Select all transactions** was used, all invoice line details from the previously confirmed invoice are copied to the new draft. 

The following are some of the key points to understand about the line details on the new corrected invoice:

- All quantities are updated to zero. The application assumes that all invoiced items are fully credited. If needed, you can manually update these quantities to reflect the quantity that is being invoiced, and not the quantity that is being credited. Based on the quantity you enter, the application calculates the credited quantity. This amount is reflected in the actuals that are created when the corrected invoice is confirmed. If you are making changes to the tax amount, you must enter the correct tax amount and not the tax amount that is being credited.
- Previously confirmed product-based contract lines are not copied over. Processing corrections on a product-based project invoice is not supported.
- Milestone corrections are always processed as full credits.
- Retainer or advance amounts can be corrected if the customer was invoiced for an incorrect amount.
- Reconciliations of retainers and advances can be corrected if an incorrect amount was used to reconcile against the charges on a previously confirmed invoice.

> [!IMPORTANT]
> Invoice line details that are corrections to other already invoiced charges have the field **Correction** set to **Yes**. Invoices that have corrected invoice line details have a field called **Has corrections** that is also set to **Yes**.

## Actuals created when a revised invoice is confirmed

The following table lists the actuals that are created when a corrective invoice is confirmed.

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="216" valign="top">
                <p>
                    <strong>Scenario</strong>
                </p>
            </td>
            <td width="808" valign="top">
                <p>
                    <strong>Actuals created on confirmation</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="4" valign="top">
                <p>
                    Confirm the correction of an invoiced advance or
                    retainer.<strong></strong>
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal of the retainer or advance that
                    was created for reconciliation. This amount is positive because it is
                    meant to cancel out the negative that was created when the retainer or advance was invoiced.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal actual is created
                    for the amount on the retainer or advance to reverse the
                    original billed sales.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new billed sales actual is created for
                    the corrected amount on the retainer or advance-based
                    corrected invoice line.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    An unbilled sales actual of negative amount of the retainer
                    or advance-based corrected invoice line, which will be used for
                    reconciliation.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="4" valign="top">
                <p>
                    A confirmation of the correction of a previously reconciled
                    retainer or advance.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal of the retainer or advance that
                    was created for reconciliation. This amount is positive and is
                    meant to cancel out the negative that was created when the previous reconciliation occurred.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal actual for the amount on
                    the previous invoice.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new billed sales actual for the corrected retainer amount
                    that is applied on the corrected invoice.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    An unbilled sales actual with a negative amount from the
                    corrected leftover retainer or advance, which will be used
                    for reconciliation on later invoices.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced time
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the hours and amount on the
                    original invoice line detail for time.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual for the hours and amount on the
                    original invoice line detail for time.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing the partial credit on a time transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the hours and amount invoiced
                    on the original invoice line detail for time.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    hours and amount on the edited invoice
                    line detail, a reversal of this, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    remaining hours and amount after deducting the corrected
                    figures on the invoice line detail.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced expense
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount on the
                    original invoice line detail for the expense.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual for the quantity and amount on
                    the original invoice line detail for the expense.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing the partial credit of a previously invoiced expense
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount
                    invoiced on the original invoice line detail for an expense.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    quantity and amount on the corrected invoice
                    line detail, a reversal of this, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    remaining quantity and amount after deducting the corrected
                    figures on the invoice line detail.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced material
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount on the
                    original invoice line detail for material.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual for the quantity and amount on the
                    original invoice line detail for material.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing the partial credit on a material transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount invoiced
                    on the original invoice line detail for material.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    quantity and amount on the edited invoice
                    line detail, a reversal of this, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    remaining quantity and amount after deducting the corrected
                    figures on the invoice line detail.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced fee
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount on the
                    original invoice line detail for the fee.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual for the quantity and amount on
                    the original invoice line detail for the fee.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the partial credit of a previously invoiced fee
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the quantity and amount
                    invoiced on the original invoice line detail for fee.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    quantity and amount on the edited corrective invoice
                    line detail, a reversal of this, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced milestone.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the amount on the original
                    invoice line detail for the milestone.
                </p>
                <p>
                    The invoice status of the milestone is updated from <b>Customer Invoice Posted</b> to <b>Ready to Invoice</b>.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" valign="top">
                <p>
                    Invoicing the partial credit of a previously invoiced
                    milestone.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    Unsupported
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" valign="top">
                <p>
                    Credits and corrections of a previously invoiced product-based contract line.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    Unsupported
                </p>
            </td>
        </tr>
    </tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
