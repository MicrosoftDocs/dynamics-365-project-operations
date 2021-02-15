---
title: Confirm a proforma invoice
description: This topic provides information about confirming a proforma invoice. 
author: rumant
manager: AnnBe
ms.date: 10/13/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: rumant
---

# Confirm a proforma invoice

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

After a proforma invoice is confirmed, the status of the project invoice updates to **Confirmed**. When an invoice is confirmed, it becomes read-only. Going forward, the invoice can only be corrected if there are any customer-initiated corrections or credits, or when it's marked as paid.

The following table lists the actuals created by the system. These actuals are created when certain operations are performed on the draft project invoice before it is confirmed.

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="416" valign="top">
                <p>
                    <strong>Scenario</strong>
                </p>
            </td>
            <td width="608" valign="top">
                <p>
                    <strong>Actuals created on confirmation</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing a time transaction without any edits on the draft
                    invoice.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the hours and amount on the
                    original time approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the hours and amount on the
                    original time approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing a time transaction that was edited to reduce the
                    quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the hours and amount on the
                    original time approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    hours and amount on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is non-chargeable for the
                    remaining hours and amount after deducting the corrected
                    figures on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing a time transaction that was edited to increase
                    the quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the hours and amount on the
                    original time approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    hours and amount on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing an expense transaction without any edits on the draft
                    invoice.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on
                    the original expense approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the quantity and amount on the
                    original expense approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing an expense transaction that was edited to reduce
                    the quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on
                    the original expense approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for the
                    quantity and amount on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual. 
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is non-chargeable for the
                    remaining quantity and amount after deducting the corrected
                    figures on edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent of the billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing an expense transaction that was edited to
                    increase the quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on
                    the original expense approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is chargeable for quantity
                    and amount on the edited invoice line detail, a reversal of the untilled sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing a fee.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the fee amount on the
                    original journal line.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the quantity and amount on the
                    original fee journal line.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" valign="top">
                <p>
                    Invoicing a milestone.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the milestone amount on the
                    original milestone on the project contract line.
                </p>
            </td>
        </tr>
    </tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]