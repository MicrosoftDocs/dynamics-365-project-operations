---
title: Invoice a retainer or an advance
description: This article provides information about how to invoice a retainer or an advance in Project Operations.
author: suvaidya
ms.author: nshrivastava
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Invoice a retainer or an advance

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations supports retainer-based contracts and one-time advances. On a project contract, you can record a schedule of retainers or a one-time advance. However, recording at the project contract level doesn't immediately make a retainer or advance available for use. To use a retainer or advance on an invoice that actually charges the customer, the retainer or advance must be invoiced first.

Complete the following steps to invoice a retainer or an advance.

1. Select **Sales** > **Billing** > **Retainers and Advances**. 
2. On the **Advances and Retainers** page, use the filter to select the specific retainer or advance to invoice and mark it as **Ready to Invoice**.
3. Create an invoice either manually from the **Project Contract** list or detail page. The retainer or advance is shown on the draft invoice in the **Advances and Retainers** section on the **Invoice** page.
4. Confirm the invoice. This will make the retainer or advance available for use. You can verify the invoice on the **Retainers and Advances** list page. For an invoiced Advance or Retainer, the available amount is shown in the grid.

## Create a retainer or advance from the Invoice grid

You can create a retainer or an advance directly on an invoice.

1. On a draft invoice, on the **Advances and Retainers** subgrid, select **New** to create a new retainer or advance. 
2. On the **Quick Create** page, add the necessary information, and then select **Save**. The retainer or advance is created on the project contract related to the invoice. The retainer or advance is automatically marked as **Ready to Invoice** and then added to the **Advances and Retainers** subgrid on the **Invoice** page.

## Reconcile an invoiced retainer or advance

After a retainer or advance is invoiced, they can be used or reconciled on an invoice with time, expenses, milestones, or other project-based charges. The customer will see their invoice amount reduced by the retainer or advance amount used on this invoice.

On every invoice that is generated for a project contract that has invoiced retainers or advances, Project Operation automatically applies the retainer or advance to the invoice.

This can be seen in the **Applied Retainers and Advances** grid on the **Invoice** page. The following table provides information about the fields on the **Applied Retainers and Advances** grid of the **Project Invoice** page.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Description | **Applied Advances and Retainers** grid on the **Project Invoice** page |This read-only field provides a description of the retainer or advance used on this invoice. This value can't be changed on the invoice. This value can be updated on the subgrid on the **Project Contract** page. | This field can be displayed to the customer on the printed invoice to indicate which retainer or advance is applied on the invoice. |
| Delivered On | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the invoice date of the retainer or advance used on this invoice. This value can't be changed on the invoice. This value can be updated on the subgrid on the **Project Contract** page. | This field can be displayed to the customer on the printed invoice to indicate the date when the retainer or advance was first invoiced to the customer. |
| Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the amount of the retainer or advance used on this invoice. This value can't be changed on the invoice. This value can be updated on the subgrid on the **Project Contract** page. | This field can be displayed to the customer on the printed invoice to indicate the original amount of retainer or advance that was paid by the customer. |
| Used Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the calculated value that summarizes how much of the retainer or advance has been used. | This field can be displayed to the customer on the printed invoice to indicate the amount from this retainer or advance that was already used. |
| Extended Amount | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This editable field provides the amount of the retainer or advance that is being used on this project invoice. This amount can't be more that what is available on the advance. The system automatically calculates this as the difference between the **Amount** and **Used Amount** fields on the grid. You can decrease this amount to use less than what is available but you can't increase the amount to use more than what is available. | This field can be displayed to the customer on the printed invoice to indicate the amount from this retainer or advance that being used on the invoice. |
| Balance Retainer Amount. | **Applied Advances and Retainers** grid on the **Project Invoice** page  | This read-only field provides the value of how much of the retainer or advance will be left after the invoice is confirmed. | This field can be displayed to the customer on the printed invoice to indicate the amount that will be left from this retainer or advance after the invoice is confirmed and paid. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
