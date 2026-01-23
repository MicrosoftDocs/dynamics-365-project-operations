---
title: Manage a proforma project-based invoice
description:  This article provides information about how to manage and work with proforma project-based invoices.
author: suvaidya
ms.author: nshrivastava
ms.custom: 
  - bap-template
ms.date: 06/10/2024
ms.topic: how-to
ms.reviewer: johnmichalak

---

# Manage a proforma project-based invoice

_**Applies To:** Project Operations Integrated with ERP_

In Dynamics 365 Project Operations, proforma invoices are built as an extension to the invoices in Dynamics 365 Sales. However, there are many differences in the invoicing process between Sales and Project Operations when it comes to invoicing. For example, it's not possible to create a new invoice from the **Invoices List** page in Project Operations, but it is possible to do so in Sales. These differences and extensions are in place to support invoicing processes for projects that are different from a typical invoice for a sales order.

> [!IMPORTANT]
> Because of the differences, don't use invoices in Sales and Project Operations interchangeably.

## Invoice header

The following information is available on a proforma invoice header in Project Operations.

| Field | Location | Description |
| --- | --- | --- | 
| **Invoice ID** | **Summary** tab | The ID that is generated automatically when a proforma invoice is created. A read-only field that is locked from editing. This field is used as a reference for each proforma invoice. |
| **Name** | **Summary** tab | Set to the name of the project contract by default. This field can be edited. | 
| **Currency** | **Summary** tab | Set to the currency of the project contract by default. A read-only field that is locked from editing. |
| **Price list** | **Summary** tab | Set to the price list of the project contract by default. A read-only field that is locked from editing. | 
| **Opportunity** | **Summary** tab | The reference to the linked opportunity. A read-only field that is locked from editing. | 
| **Contract** | **Summary** tab | The reference to the linked project contract. A read-only field that is locked from editing. | 
| **Customer** | **Summary** tab | The reference to the linked project contract. A read-only field that is locked from editing. |
| **Description** | **Summary** tab | The text field that describes the invoice. This field can be edited. | 
| **Bill To** and related fields | **Summary Tab** | Defaults are set from the project contract customer. This field can be edited.  | 
| **Status** | **Summary** tab | Sets the following options: **Active**, **Closed**, **Paid**, and **Canceled**, and can be edited. Unsupported statuses for Project Operations include **Closed** and **Canceled**. </br> The status is set to **Active** when the invoice is created. </br>The status should be set to **Paid** only after the invoice is confirmed.  | 
| **Project Invoice Status** | **Summary** tab | Sets the following options: **Draft**, **In review**, and **Confirmed**, and can be edited. In both **Draft** and **In Review** statuses, the invoice can be edited. The invoice can't be edited after it's confirmed. | 
| **Detail Amount** | **Summary** tab | The sum of amounts on all the invoice lines after advances and deductions. A read-only field that is locked from editing.  This field is used to calculate the final amount. | 
| **Discount (%)** | **Summary** tab | This field can be edited to enter a discount percentage. This field is not supported by Project Operations functionality. This is an unsupported field.|  
| **Discount Amount** | **Summary** tab | This field can be edited to enter the discount amount. This field is not supported by Project Operations functionality. This is an unsupported field. |  
| **Pre-freight Amount** | **Summary Tab** | The total invoice amount after discounts are applied. A read-only field that is locked from editing. This field is used to calculate the final amount.  | 
| **Freight Amount** | **Summary** tab | This field can be edited to enter freight amount. This field is not supported by Project Operations functionality. This is an unsupported field. |
| **Total Tax** | **Summary** tab | The total tax from all invoice lines on the invoice. A read-only field that is locked from editing. | 
| **Total Amount** | **Summary** tab | The sum of the amount after discounts and taxes. The sum is the amount the customer needs to pay. | 

## Project-based invoice Lines

In Project Operations, there is always one invoice line for every project contract line. The invoice line is created even if there are no actuals. The following information is available on a proforma invoice line.

| Field | Location | Description | 
| --- | --- | --- |
| **Invoice ID** | **General** tab | The reference to the invoice ID. A read-only field that is locked from editing. The invoice ID link can be used to navigate back to the invoice header. | 
| **Name** | **General** tab | The name of the invoice line set by default from the contract line name. This field can be edited. |
| **Project** | **General** tab | The project on the related project contract line. A read-only field that is locked from editing. The project link can be used to navigate to the project. | 
| **Billing Method** | **General** tab | The billing method on the related project contract line. A read-only field that is locked from editing. |
| **Contract Line Amount** | **General** tab | The contract amount on the related project contract line. A read-only field that is locked from editing. | 
| **Invoiced till Date** | **General** tab | The sum of amounts on all the invoice line details of this invoice. A read-only field that is locked from editing. | 
| **Amount** | **General** tab | The sum of amounts on all chargeable invoice line details of this invoice. A read-only field that is locked from editing. This field is used to calculate the final amount on the invoice header. | 
| **Tax** | **General** tab | The sum of tax amounts on all the invoice line details of this invoice line. A read-only field that is locked from editing. This field is used to calculate the final tax amount on the invoice header. | 
| **Extended Amount** | **General** tab | The sum of total amounts (**Tax + Amounts**) on all chargeable invoice line details of this invoice line. A read-only field that is locked from editing. This field is used to calculate the final amount on the invoice header. |

## Invoice line details

Each invoice line in a project invoice includes invoice line details. These line details are related to the unbilled sales actuals and milestones that relate to the contract line referenced by the invoice line. All these transactions are marked **Ready to Invoice**.

For a **Time and Material Invoice** line, invoice line details are grouped into **Chargeable**, **Non-chargeable**, and **Complimentary** on the **Invoice Line** page. **Chargeable Invoice Line** details add up to the invoice line total. **Complimentary** and **Non-chargeable Actuals** do not add up to the invoice line total.

For a **Fixed Price Invoice** line, invoice line details are created from milestones that are marked as **Ready to invoice** on the related contract line. After the invoice line detail is created from a milestone, the billing status on the milestone updates to **Customer Invoice Created**.

### Edit invoice line details

The following fields are available on the invoice line detail that is backed by an unbilled sales actual.

| Field | Description |
| --- | --- | 
| **Invoice line** | A reference to the **Invoice Line ID**. This field is read only and locked for editing. This link can be used to navigate back to the invoice header. | 
| **Description** | A description of the invoice line detail. Set by default from the **Internal Comments** field on the **Time Entry**, and from the **Description** field on **Expense Entry**. The field can be edited.| 
| **External Description** | A description of the invoice line detail. Set by default from the **External Comments** field on the **Time Entry**, and the **Description** field on **Expense Entry**. The field can be edited. This description can be used to determine what should be on the printed invoice that will be sent to the customer. In Project Operations, a proforma invoice doesn't have all the required functionality to configure print settings for an invoice. | 
| **Start Date** | This is a read-only field that is set by default from the source actual. |
| **Project** | This is a read-only field that is set by default from the source actual to the project on the related contract line. |  
| **Task** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Transaction category** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Role** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Bookable Resource** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Resourcing Company** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Resourcing Unit** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Quantity** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Unit Schedule** | For invoice line detail for time, this is always set to time and can't be edited. For expenses, this is set by default from the source expense actual. A read-only field that is locked from editing. | 
| **Unit** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Price** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Currency** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Amount** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Tax** | Set by default from the source actual. The field can be edited.| 
| **Extended Amount** | A calculated field, calculated as **Amount + Tax**. A read-only field that is locked from editing. | 
| **Billing Type** | Set by default from the source actual. The field can be edited. Selecting **Chargeable** adds the line to the invoice line total. **Complimentary** and **Non-chargeable** will exclude it from the invoice line total.| 
| **Select Product** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Product** | Set by default from the source actual. A read-only field that is locked from editing. | 
| **Product Name** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Write In Description** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Transaction Type** | This is a read-only field that is set by default from the source actual to **Billed Sales**. |  
| **Transaction Class** | Set by default from the source actual. A read-only field that is locked from editing. | 

The following fields are available on an invoice line detail that is backed by a milestone.

| Field | Description |
| --- | --- | 
| **Invoice line** | Reference to the **Invoice Line ID**. A read-only field that is locked from editing. The link can be used to navigate back to the invoice header.  | 
| **Description** | Description of the invoice line detail. Set by default from the description of the source milestone. | 
|**External Description** | Description of the invoice line detail that is set by default from the description of the source milestone. This field can be used to determine what should be on the printed invoice that will be sent to the customer. A proforma invoice in Project Operations doesn't have all the required functionality to configure print settings for an invoice. | 
| **Start Date** | Set by default from the **Milestone** date on source milestone. A read-only field that is locked from editing. | 
| **Project** | Set by default from the source milestone. A read-only field that is locked from editing. |
| **Task** | Set by default from the source milestone. A read-only field that is locked from editing. | 
| **Transaction category** | A read-only field that is locked from editing. |
| **Role** | A read-only field that is locked from editing. | 
| **Bookable Resource** | A read-only field that is locked from editing. | 
| **Resourcing Unit** | A read-only field that is locked from editing. | 
| **Unit Schedule** | A read-only field that is locked from editing. | 
| **Unit** | A read-only field that is locked from editing. | 
| **Price** | Set by default from the amount on the source milestone. A read-only field that is locked from editing. |
| **Currency** | Set by default from the source milestone. A read-only field that is locked from editing. |
| **Amount** | Set by default from the amount on the source milestone. A read-only field that is locked from editing. | 
| **Tax** | Set by default from the tax amount on the source milestone. A read-only field that is locked from editing. |
| **Extended Amount** | Set by default from the extended amount on the source milestone. The field can be edited. | 
| **Billing Type** | Always set by default to **Chargeable**. A read-only field that is locked from editing. |
| **Transaction Type** | Set by default from the source milestone. A read-only field that is locked from editing. | 
| **Transaction Class** | Set by default from the source milestone. A read-only field that is locked from editing. | 

## Refresh invoice transactions

If you have actuals that came in after the invoice was created, you can include these actuals on the invoice.

1. In the **Billing Backlog View**, mark the data as **Ready to Invoice**.   
2. Open the draft proforma invoice and, on the **Actions** ribbon, select **Refresh Invoice Line Transactions**.

  Invoice line details are created for any actual that is past dated and marked as **Ready to Invoice**, but isn't included on the invoice.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
