---
title: Confirm a proforma project invoice 
description: This article provides information about confirming proforma project invoices in Project Operations.
author: suvaidya
ms.date: 11/18/2023
ms.topic: how-to
ms.custom: 
  - bap-template
  - evergreen
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Confirm a proforma project invoice 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_


After a proforma invoice is confirmed, the status of the project invoice updates to **Confirmed**. When an invoice is confirmed, it becomes read-only. Going forward, the invoice can only be corrected if there are any customer-initiated corrections or credits.

The following table lists the actuals created by the system. These actuals are created when certain operations are performed on the draft project invoice before it is confirmed.

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
                    Invoicing an advance or retainer
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales actual of type, <strong>Retainer</strong> is created for the
                    amount on the advance or retainer.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    An unbilled sales actual of a negative amount of the retainer
                    or advance to be used for reconciliation.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    After fully reconciling a retainer or advance on an invoice.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal of the retainer or advance that
                    was created for reconciliation. This amount is positive as
                    it's meant to cancel out the negative that was created when the retainer or advance was invoiced.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the amount on this
                    invoice.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    After partially reconciling a retainer or advance on an
                    invoice.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal of the retainer or advance that
                    was created for reconciliation. This amount is positive as
                    it's meant to cancel out the negative that was created when the retainer or advance was invoiced.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the amount on this
                    invoice.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A negative unbilled sales actual of the remaining retainer or advance amount to be used for
                    reconciliation on future invoices.
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
                    hours and amount on the edited invoice line detail, a reversal of the sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual that is non-chargeable for the
                    remaining hours and amount after deducting the corrected
                    figures on edited invoice line detail, a reversal of the sales actual, and an equivalent billed sales actual.
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
                    Invoicing an expense transaction without any edits on draft
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
                    original expense approval
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
                    figures on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual.
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
                    and amount on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual. 
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing a material transaction without any edits on the draft
                    invoice.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on the
                    original material usage approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the quantity and amount on the
                    original material usage approval.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="3" valign="top">
                <p>
                    Invoicing a material transaction that was edited to reduce the
                    quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on the
                    original time approval.
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
                    figures on the edited invoice line detail, a reversal of the unbilled sales actual, and an equivalent billed sales actual.
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing a material transaction that was edited to increase
                    the quantity.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    An unbilled sales reversal for the quantity and amount on the
                    original material usage approval.
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
        <tr>
            <td width="216" valign="top">
                <p>
                    Invoicing a product-based contract line.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales actual for the product line with the quantity
                    and amount coming from the product-based contract line.
                </p>
            </td>
        </tr>
    </tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
