---
title: Revise project invoices
description: This article provides information about how to revise project invoices in Project Operations.
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

**Select transactions** – Use this option to revise only specific transactions on the confirmed invoice.

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

- All quantities are updated to zero. Dynamics 365 Project Operations assumes that all invoiced items are fully credited. If needed, you can manually update these quantities to reflect the quantity that is being invoiced, and not the quantity that is being credited. Based on the quantity you enter, the application calculates the credited quantity. This amount is reflected in the actuals that are created when the corrected invoice is confirmed. If you are making changes to the tax amount, you must enter the correct tax amount and not the tax amount that is being credited.
- Milestone corrections are always processed as full credits.


> [!IMPORTANT]
> For invoice line details that are corrections to other already invoiced charges, the **Correction** field is set to **Yes**. For invoices that have corrected invoice line details, the **Has corrections** field is set to **Yes**.

## Actuals created when a corrective invoice is confirmed

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
                    This scenario isn't supported.
                </p>
            </td>
        </tr>       
    </tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
