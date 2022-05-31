---
title: Create corrective project-based invoices 
description: This article provides information about corrective invoices in Project Operations.
author: rumant
ms.date: 03/29/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Create corrective project-based invoices 

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A confirmed project invoice can be corrected to process changes or credits as negotiated with the customer and project manager.

To make edits to a confirmed invoice, open the confirmed invoice and select **Correct this Invoice**. 

> [!NOTE]
> This selection isn't available unless a project invoice is confirmed.

A new draft invoice is created from the confirmed invoice. All invoice line details from the previously confirmed invoice are copied to the new draft. The following are some key points to help you understand more about the line details on the new corrected invoice:

- All quantities are updated to zero. This assumes that all invoiced items are fully credited. If needed, you can manually update these quantities to reflect the quantity that is being invoiced, and not the quantity that is being credited. Based on the quantity you enter, the application calculates the credited quantity. This amount is reflected in the actuals that are created when the corrected invoice is confirmed. If you are making changes to the tax amount, you must enter the correct tax amount and not the tax amount that is being credited.
- Milestone corrections are always processed as full credits.
- Retainer or advance amounts can be corrected if the customer was invoiced for an incorrect amount.
- Reconciliations of retainers and advances can be corrected if an incorrect amount was used to reconcile against the charges on a previously confirmed invoice.

> [!IMPORTANT]
> Invoice line details that are corrections to other already invoiced charges have the **Correction** field set to **Yes**. Invoices that have corrected invoice line details have a field called **Has corrections** that is also set to **Yes**.

## Actuals created on confirmation of a corrective invoice

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
                    The invoice status on the milestone is updated from <b>Customer invoice posted</b> to <b>Ready to Invoice</b>.
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
    </tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
