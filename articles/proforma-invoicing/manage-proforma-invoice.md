---
title: Manage a proforma project-based invoice
description:  This article provides information about how to manage and work with proforma project-based invoices.
author: suvaidya
ms.author: nshrivastava
ms.custom: 
  - bap-template
ms.date: 01/23/2026
ms.topic: how-to
ms.reviewer: johnmichalak

---

# Manage a proforma project-based invoice

_**Applies To:** Project Operations Integrated with ERP_

In Dynamics 365 Project Operations, proforma invoices extend the invoices in Dynamics 365 Sales. However, many differences exist in the invoicing process between Sales and Project Operations. For example, you can't create a new invoice from the **Invoices List** page in Project Operations, but you can create a new invoice in Sales. These differences and extensions exist to support invoicing processes for projects that differ from a typical invoice for a sales order.

> [!IMPORTANT]
> Don't use invoices in Sales and Project Operations interchangeably because of the differences.

## Invoice header

The following information is available on a proforma invoice header in Project Operations.

| Field | Location | Description |
| --- | --- | --- |
| **Invoice ID** | **Summary** tab | The ID that the system generates automatically when you create a proforma invoice. It's a read-only field that you can't edit. Use this field as a reference for each proforma invoice. |
| **Name** | **Summary** tab | The name of the project contract, which is the default value. You can edit this field. |
| **Currency** | **Summary** tab | The currency of the project contract, which is the default value. It's a read-only field that you can't edit. |
| **Price list** | **Summary** tab | The price list of the project contract, which is the default value. It's a read-only field that you can't edit. |
| **Opportunity** | **Summary** tab | The reference to the linked opportunity. It's a read-only field that you can't edit. |
| **Contract** | **Summary** tab | The reference to the linked project contract. It's a read-only field that you can't edit. |
| **Customer** | **Summary** tab | The reference to the linked project contract. It's a read-only field that you can't edit. |
| **Description** | **Summary** tab | The text field that describes the invoice. You can edit this field. |
| **Bill To** and related fields | **Summary Tab** | The project contract customer provides the default values. You can edit this field.  |
| **Status** | **Summary** tab | Sets the following options: **Active**, **Closed**, **Paid**, and **Canceled**, and can be edited. Project Operations doesn't support the **Closed** and **Canceled** statuses. </br> The status is set to **Active** when you create the invoice. </br>You should set the status to **Paid** only after you confirm the invoice.  |
| **Project Invoice Status** | **Summary** tab | Sets the following options: **Draft**, **In review**, and **Confirmed**, and can be edited. In both **Draft** and **In Review** statuses, you can edit the invoice. You can't edit the invoice after it's confirmed. |
| **Detail Amount** | **Summary** tab | The sum of amounts on all the invoice lines after advances and deductions. It's a read-only field that you can't edit.  Use this field to calculate the final amount. |
| **Discount (%)** | **Summary** tab | Enter a discount percentage. Project Operations functionality doesn't support this field. This is an unsupported field.|  
| **Discount Amount** | **Summary** tab | Enter the discount amount. Project Operations functionality doesn't support this field. This is an unsupported field. |  
| **Pre-freight Amount** | **Summary Tab** | The total invoice amount after discounts are applied. It's a read-only field that you can't edit. Use this field to calculate the final amount.  |
| **Freight Amount** | **Summary** tab | Enter freight amount. Project Operations functionality doesn't support this field. This is an unsupported field. |
| **Total Tax** | **Summary** tab | The total tax from all invoice lines on the invoice. It's a read-only field that you can't edit. |
| **Total Amount** | **Summary** tab | The sum of the amount after discounts and taxes. The sum is the amount the customer needs to pay. |

## Project-based invoice lines

In Project Operations, each project contract line has a corresponding invoice line. The system creates the invoice line even if there are no actuals. A proforma invoice line shows the following information.

| Field | Location | Description |
| --- | --- | --- |
| **Invoice ID** | **General** tab | The reference to the invoice ID. A read-only field that you can't edit. Use the invoice ID link to go back to the invoice header. |
| **Name** | **General** tab | The name of the invoice line set by default from the contract line name. You can edit this field. |
| **Project** | **General** tab | The project on the related project contract line. A read-only field that you can't edit. Use the project link to go to the project. |
| **Billing Method** | **General** tab | The billing method on the related project contract line. A read-only field that you can't edit. |
| **Contract Line Amount** | **General** tab | The contract amount on the related project contract line. A read-only field that you can't edit. |
| **Invoiced till Date** | **General** tab | The sum of amounts on all the invoice line details of this invoice. A read-only field that you can't edit. |
| **Amount** | **General** tab | The sum of amounts on all chargeable invoice line details of this invoice. A read-only field that you can't edit. Use this field to calculate the final amount on the invoice header. |
| **Tax** | **General** tab | The sum of tax amounts on all the invoice line details of this invoice line. A read-only field that you can't edit. Use this field to calculate the final tax amount on the invoice header. |
| **Extended Amount** | **General** tab | The sum of total amounts (**Tax + Amounts**) on all chargeable invoice line details of this invoice line. A read-only field that you can't edit. Use this field to calculate the final amount on the invoice header. |

## Invoice line details

Each invoice line in a project invoice includes invoice line details. These line details relate to the unbilled sales actuals and milestones that relate to the contract line the invoice line references. Mark all these transactions as **Ready to Invoice**.

For a **Time and Material Invoice** line, the **Invoice Line** page groups invoice line details into **Chargeable**, **Non-chargeable**, and **Complimentary**. **Chargeable Invoice Line** details add up to the invoice line total. **Complimentary** and **Non-chargeable Actuals** don't add up to the invoice line total.

For a **Fixed Price Invoice** line, invoice line details come from milestones that you mark as **Ready to invoice** on the related contract line. After the system creates the invoice line detail from a milestone, it updates the billing status on the milestone to **Customer Invoice Created**.

### Edit invoice line details

The following fields are available on the invoice line detail that is backed by an unbilled sales actual.

| Field | Description |
| --- | --- |
| **Invoice line** | A reference to the **Invoice Line ID**. This field is read only and locked for editing. Use this link to go back to the invoice header. |
| **Description** | A description of the invoice line detail. Set by default from the **Internal Comments** field on the **Time Entry**, and from the **Description** field on **Expense Entry**. You can edit this field.|
| **External Description** | A description of the invoice line detail. Set by default from the **External Comments** field on the **Time Entry**, and the **Description** field on **Expense Entry**. You can edit this field. Use this description to determine what should be on the printed invoice that you send to the customer. In Project Operations, a proforma invoice doesn't have all the required functionality to configure print settings for an invoice. |
| **Start Date** | This is a read-only field that is set by default from the source actual. |
| **Project** | This is a read-only field that is set by default from the source actual to the project on the related contract line. |  
| **Task** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Transaction category** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Role** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Bookable Resource** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Resourcing Company** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Resourcing Unit** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Quantity** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Unit Schedule** | For invoice line detail for time, this value is always set to time and can't be edited. For expenses, this value is set by default from the source expense actual. A read-only field that is locked from editing. |
| **Unit** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Price** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Currency** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Amount** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Tax** | Set by default from the source actual. You can edit this field.|
| **Extended Amount** | A calculated field, calculated as **Amount + Tax**. A read-only field that is locked from editing. |
| **Billing Type** | Set by default from the source actual. You can edit this field. Selecting **Chargeable** adds the line to the invoice line total. **Complimentary** and **Non-chargeable** exclude it from the invoice line total.|
| **Select Product** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Product** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Product Name** | Set by default from the source actual. A read-only field that is locked from editing. |  
| **Write In Description** | Set by default from the source actual. A read-only field that is locked from editing. |
| **Transaction Type** | This is a read-only field that is set by default from the source actual to **Billed Sales**. |  
| **Transaction Class** | Set by default from the source actual. A read-only field that is locked from editing. |

The following fields are available on an invoice line detail that is backed by a milestone.

| Field | Description |
| --- | --- |
| **Invoice line** | Reference to the **Invoice Line ID**. A read-only field that is locked from editing. Use the link to go back to the invoice header.  |
| **Description** | Description of the invoice line detail. Set by default from the description of the source milestone. |
|**External Description** | Description of the invoice line detail that is set by default from the description of the source milestone. Use this field to determine what should be on the printed invoice that you send to the customer. A proforma invoice in Project Operations doesn't have all the required functionality to configure print settings for an invoice. |
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
| **Extended Amount** | Set by default from the extended amount on the source milestone. You can edit this field. |
| **Billing Type** | Always set by default to **Chargeable**. A read-only field that is locked from editing. |
| **Transaction Type** | Set by default from the source milestone. A read-only field that is locked from editing. |
| **Transaction Class** | Set by default from the source milestone. A read-only field that is locked from editing. |

## Refresh invoice transactions

If actuals arrive after you create the invoice, you can add these actuals to the invoice.

1. In the **Billing Backlog View**, mark the data as **Ready to Invoice**.
1. Open the draft proforma invoice and, on the **Actions** ribbon, select **Refresh Invoice Line Transactions**.

  The process creates invoice line details for any actual that is past dated and marked as **Ready to Invoice**, but isn't included on the invoice.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
