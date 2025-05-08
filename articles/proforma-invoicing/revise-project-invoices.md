---
title: Revise (correct) project invoices
description: This article provides information about how to revise project invoices in Project Operations.
author: suvaidya    
ms.date: 12/15/2023
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Revise (correct) project invoices

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

A confirmed project invoice can be revised to process changes or credits as negotiated with the customer and project manager.

To make edits to a confirmed invoice, open the confirmed invoice and select **Revise** (previously referred to as **Correct this invoice**). 

> [!NOTE]
> Beginning UR 37,  the invoice revision process has been significantly improved to include the **Select transactions** capability so you can perform edits quickly and process invoice corrections in lesser duration. This also helps improve performance of invoice corrections when dealing with large invoices with hundreds or thousands of invoice line details, but requiring to correct only a few of those transactions.   

Depending on the need for correction, users can choose between 2 options - **Select transactions** to revise selected transactions or **Select all transactions** to revise the entire invoice. 

1. **Select transactions** – Use this option to revise **specific** transactions on the confirmed invoice.
    - Selecting this option opens a dialog with a list of previously invoiced transactions categorized by transaction types of **Time and Material**, **Milestones**, and **Advances and Retainers**.
    - Select the invoice line details for revision by setting the **Revise** toggle to **Yes**.
    - Select the **Create invoice** ribbon option to create a new revised invoice with the selected transactions.
    - Select the **Add to invoice** ribbon option to append the selected transactions for revision to an existing draft invoice for the same project contract and project contract customer. 

2. **Select all transactions** – Use this option to revise **all** the transactions on the confirmed invoice.
   
> [!IMPORTANT]
The invoice correction form is not customizable. The correction form is only valid for invoices that are confirmed or paid. Invoices with custom status are not supported. 

## Revised invoice
A new draft invoice is created from the confirmed invoice. 
- If **Select transactions** was used, the selected invoice line details from the previously confirmed invoice are copied to the new draft. 
- If **Select all transactions** was used, all invoice line details from the previously confirmed invoice are copied to the new draft.
- In either case, the invoice header is updated to reflect the total amount on the invoice after correction.

The following are some of the key points to understand about the line details on the new corrected invoice:

- All quantities are updated to zero. Dynamics 365 Project Operations assumes that all invoiced items are fully credited. If needed, you can manually update these quantities to reflect the quantity that is    being invoiced, and not the quantity that is being credited. Based on the quantity you enter, the application calculates the credited quantity. This amount is reflected in the actuals that are created       when the corrected invoice is confirmed. If you're making changes to the tax amount, you must enter the correct tax amount and not the tax amount that is being credited.
- Milestone corrections are always processed as full credits.
- Product based lines corrections cannot be corrected using the revise option but instead can be adjusted manually using journals. 

> [!NOTE]
> To use the **Revise** feature with the **Select transactions** capability, turn on the Invoice revision updates feature at **Settings** > **Parameters** > **Feature control** > **Invoice Revision updates**.

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
