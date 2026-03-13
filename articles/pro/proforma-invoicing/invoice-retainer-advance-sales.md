---
title: Invoice a retainer or an advance
description: This article provides information about how to invoice a retainer or an advance in Project Operations.
author: suvaidya
ms.author: nshrivastava
ms.date: 03/13/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Invoice a retainer or an advance

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations supports retainer-based contracts and one-time advances. On a project contract, you can record a schedule of retainers or a one-time advance. However, recording at the project contract level doesn't immediately make a retainer or advance available for use. To use a retainer or advance on an invoice that actually charges the customer, you must first invoice the retainer or advance.

Complete the following steps to invoice a retainer or an advance.

1. Select **Sales** > **Billing** > **Retainers and Advances**.
1. On the **Advances and Retainers** page, use the filter to select the specific retainer or advance to invoice and mark it as **Ready to Invoice**.
1. Create an invoice either manually from the **Project Contract** list or detail page. The retainer or advance is shown on the draft invoice in the **Advances and Retainers** section on the **Invoice** page.
1. Confirm the invoice. This step makes the retainer or advance available for use. You can verify the invoice on the **Retainers and Advances** list page. For an invoiced advance or retainer, the available amount is shown in the grid.

## Create a retainer or advance from the Invoice grid

You can create a retainer or an advance directly on an invoice.

1. On a draft invoice, in the **Advances and Retainers** subgrid, select **New** to create a new retainer or advance.
1. On the **Quick Create** page, add the necessary information, and then select **Save**. The retainer or advance is created on the project contract related to the invoice. The retainer or advance is automatically marked as **Ready to Invoice** and then added to the **Advances and Retainers** subgrid on the **Invoice** page.

## Reconcile an invoiced retainer or advance

After you invoice a retainer or advance, use it to reconcile an invoice with time, expenses, milestones, or other project-based charges. The customer sees their invoice amount reduced by the retainer or advance amount used on this invoice.

On every invoice that you generate for a project contract with invoiced retainers or advances, Project Operations automatically applies the retainer or advance to the invoice.

You can see this application in the **Applied Retainers and Advances** grid on the **Invoice** page. The following table provides information about the fields on the **Applied Retainers and Advances** grid of the **Project Invoice** page.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Description | **Applied Advances and Retainers** grid on the **Project Invoice** page |This read-only field provides a description of the retainer or advance used on this invoice. You can't change this value on the invoice. You can update this value on the subgrid on the **Project Contract** page. | You can display this field to the customer on the printed invoice to indicate which retainer or advance is applied on the invoice. |
| Delivered On | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the invoice date of the retainer or advance used on this invoice. You can't change this value on the invoice. You can update this value on the subgrid on the **Project Contract** page. | You can display this field to the customer on the printed invoice to indicate the date when the retainer or advance was first invoiced to the customer. |
| Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the amount of the retainer or advance used on this invoice. You can't change this value on the invoice. You can update this value on the subgrid on the **Project Contract** page. | You can display this field to the customer on the printed invoice to indicate the original amount of retainer or advance that the customer paid. |
| Used Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the calculated value that summarizes how much of the retainer or advance is used. | You can display this field to the customer on the printed invoice to indicate the amount from this retainer or advance that was already used. |
| Extended Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This editable field provides the amount of the retainer or advance that you're using on this project invoice. This amount can't be more than what's available on the advance. The system automatically calculates this value as the difference between the **Amount** and **Used Amount** fields on the grid. You can decrease this amount to use less than what's available but you can't increase the amount to use more than what's available. | You can display this field to the customer on the printed invoice to indicate the amount from this retainer or advance that you're using on the invoice. |
| Balance Retainer Amount. | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the value of how much of the retainer or advance is left after the invoice is confirmed. | You can display this field to the customer on the printed invoice to indicate the amount remaining from this retainer or advance after the invoice is confirmed and paid. |

## Refund unused retainers

To use the refund unused retainers feature, enable the **'Refund retainers'** feature flag.

Project-based engagements often start with retainers or advances that you invoice upfront. If a project completes with a remaining retainer balance, Project Operations lets you refund the unused amount either from a project invoice or directly from the project contract without creating separate corrective invoices. This capability simplifies financial closeout and reduces manual adjustments.

You can refund the remaining amount either from an invoice or directly from the project contract. In both cases, the refund is completed when you confirm the invoice.

### Refund a retainer from an invoice

Use this option when you're already reviewing or creating a project invoice.

To refund a retainer from and invoice, follow these steps:

1. Open an existing **draft project invoice**, or create a new one from **Billing hub**. You can create a draft invoice even if there aren't any chargeable transactions, as long as you're refunding retainers.

1. On the invoice, go to **Applied advances and retainers**.

1. Select one or more retainers with an available balance.

1. If you need to refund a retainer that's not already part of the invoice, select **Add** to add the retainer with its available amount.

1. For a newly added retainer, you can perform one of the following actions:

   - **Apply the retainer to invoice transactions**. To apply the retainer, use **Extended amount**.
   - **Refund the retainer**.

1. To refund, select the retainer and choose **Refund**. The retainer is marked as **Ready to refund**. To cancel the refund, select **Cancel refund**.

1. **Confirm the invoice** to process the refund. The retainer status is updated to **Refunded**, and the amount is returned to the customer.

### Refund a retainer from the project contract

Use this option when you close a project and no invoice exists yet.

To refund a retainer from the project contract, follow these steps:

1. Go to **Sales** > **Project contracts** and open the contract.

1. In **Advances and retainers**, select one or more retainers with an available balance.

1. Select **Refund**. The retainer is marked as **Ready to refund**.

1. Create a draft invoice, such as from **Billing hub**.

1. Review the refund in **Applied advances and retainers**, and then **confirm the invoice** to complete the refund.

### Refund status at a glance

| Status | Meaning |
|------|--------|
| **Ready to refund** | Refund is staged but not yet processed |
| **Refunded** | Refund invoice is confirmed |
| _(Blank)_ | Retainer is active or reset due to correction |

> [!NOTE]
>
> - You can’t refund more than the retainer’s available balance.  
> - Refund actions aren’t available on confirmed invoices.  
> - If a confirmed refund needs to be changed, use invoice correction or revision flows.
``

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
