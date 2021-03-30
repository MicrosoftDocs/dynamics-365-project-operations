---
# required metadata

title: Actuals 
description: This topic provides information about how to work with actuals in Microsoft Dynamics 365 Project Operations.
author: rumant
manager: AnnBe
ms.date: 09/16/2020
ms.topic: article
ms.prod: 
ms.service: project-operations
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: rumant
ms.search.validFrom: 2020-10-01
---

# Actuals 

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Actuals represent the reviewed and approved financial and schedule progress on a project. They are created as a result of approval of time, expense and material usage entries, and journal entries and invoices.

## Journal lines and time submission

For more information about time entry, see [Time entry overview](../time/time-entry-overview.md).

### Time and materials

When a time entry that is submitted is linked to a project that is mapped to a time-and-materials contract line, the system creates two journal lines, one for cost and one for unbilled sales.

### Fixed price

When a time entry that is submitted is linked to a project that is mapped to a fixed-price contract line, the system creates one journal line for cost.

### Default pricing

The logic for creating default prices resides on the journal line. The field values from the time entry are copied to the journal line. These values include the transaction date, the contract line that the project is mapped to, and the currency result in the appropriate price list.

The fields that affect default pricing, such as **Role** and **Resourcing Unit**, are used to determine the appropriate price on the journal line. You can add a custom field on the time entry. If you want the field value to be propagated to actuals, create the field on the Actuals and Journal line tables and use custom code to propagate the field value using from Time Entry to Actuals via journal line using Transaction Origins. For more information on Transaction Origins and Connections see [Linking Actuals to original records](/linkingactuals.md#example-how-transaction-origin-works-with-transaction-connection)

## Journal lines and basic expense submission

For more information about expense entry, see [Expense overview](../expense/expense-overview.md).

### Time and materials

When a basic expense entry that is submitted is linked to a project that is mapped to a time-and-materials contract line, the system creates two journal lines, one for cost and one for unbilled sales.

### Fixed price

When a basic expense entry that is submitted is linked to a project that is mapped to a fixed-price contract line, the system creates one journal line for cost.

### Default pricing

The logic for entering default prices for expenses is based on the expense category. The transaction date, the contract line that the project is mapped to, and the currency are all used to determine the appropriate price list. The fields that affect default pricing, such as **Transaction Category** and **Unit**, are used to determine the appropriate price on the journal line. However, this only works when the pricing method setup in the price list is Price per unit. If pricing method setup is At cost or Markup over cost then the price entered when the expense entry is created is used for cost and the price on the sales journal line is calculated based on the pricing method. 

You can add a custom field on the Expense entry. If you want the field value to be propagated to actuals, create the field on the Actuals and Journal line tables and use custom code to propagate the field value using from Time Entry to Actuals via journal line using Transaction Origins. For more information on Transaction Origins and Connections see [Linking Actuals to original records][Linking Actuals to original records](/linkingactuals.md#example-how-transaction-origin-works-with-transaction-connection)

## Journal lines and material usage log submission

For more information about expense entry, see [Material Usage Log](../material/material-usage-log.md).

### Time and materials

When a material usage log entry that is submitted is linked to a project that is mapped to a time-and-materials contract line, the system creates two journal lines, one for cost and one for unbilled sales.

### Fixed price

When a material usage log entry that is submitted is linked to a project that is mapped to a fixed-price contract line, the system creates one journal line for cost.

### Default pricing

The logic for entering default prices for material is based on the product and unit combination. The transaction date, the contract line that the project is mapped to, and the currency are all used to determine the appropriate price list. The fields that affect default pricing, such as **Product Id** and **Unit**, are used to determine the appropriate price on the journal line. However, this only works for catalog products. For Write -In products, the price entered when the material usage log entry is created is used for cost and sales price on the journal lines. 

You can add a custom field on the Material Usage Log entry. If you want the field value to be propagated to actuals, create the field on the Actuals and Journal line tables and use custom code to propagate the field value using from Time Entry to Actuals via journal line using Transaction Origins. For more information on Transaction Origins and Connections see [Linking Actuals to original records](/linkingactuals.md#example-how-transaction-origin-works-with-transaction-connection)

## Use entry journals to record costs

You can use entry journals to record the cost or revenue in the material, fee, time, expense, or tax transaction classes. Journals can be used for the following purposes:

- Move transaction actuals from another system to Microsoft Dynamics 365 Project Operations.
- Record costs that occurred in another system. These costs can include procurement or subcontracting costs.

> [!IMPORTANT]
> The application doesn't validate the journal line type or the related pricing that is entered on the journal line. Therefore, only a user who is fully aware of the accounting impact that actuals have on the project should use entry journals to create actuals. Because of the impact of this journal type, you should carefully choose who has access to create entry journals.

## Record actuals based on project events

Project Operations records the financial transactions that occur during a project. These transactions are recorded as actuals. The following tables show the different types of actuals that are created, depending on whether the project is a time-and-materials or fixed-price project, is in the presales stage, or is an internal project.

### The resource belongs to same organizational unit as the project's contracting unit

<table>
<thead>
<tr>
<th rowspan="3">Event</th>
<th colspan="4">Billable or sold project</th>
<th rowspan="3">Project in the presales stage</th>
<th rowspan="3">Internal project</th>
</tr>
<tr>
<th colspan="2">Time and materials</th>
<th colspan="2">Fixed price</th>
</tr>
<tr>
<th>Actuals</th>
<th>Transaction currency</th>
<th>Fixed price</th>
<th>Transaction currency</th>
</tr>
</thead>
<tbody>
<tr>
<td>A time entry is created.</td>
<td colspan="6">No activity in the Actuals entity</td>
</tr>
<tr>
<td>A time entry is submitted.</td>
<td colspan="6">No activity in the Actuals entity</td>
</tr>
<tr>
<td rowspan="2">Time is approved, and no change to or increase in billable hours occurs during approval.</td>
<td>Cost actual</td>
<td>Contracting unit currency</td>
<td rowspan="2">Cost actual</td>
<td rowspan="2">Contracting unit currency
<td rowspan="2">Cost actual</td>
<td rowspan="2">Cost actual</td>
</tr>
<tr>
<td>Unbilled sales actual – Chargeable</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="3">Time is approved, and a decrease in billable hours occurs during approval.</td>
<td>Cost actual</td>
<td>Contracting unit currency</td>
<td rowspan="3">Cost actual</td>
<td rowspan="3">Contracting unit currency</td>
<td rowspan="3">Cost actual</td>
<td rowspan="3">Cost actual</td>
</tr>
<tr>
<td>Unbilled sales actual – Chargeable for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Unbilled sales actual – Non-chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="2">An invoice is confirmed, and no change to or increase in billable hours occurs.</td>
<td>Unbilled sales reversal</td>
<td>Project contract currency</td>
<td rowspan="2">Billed sales for milestone</td>
<td rowspan="2">Project contract currency</td>
<td rowspan="2">Not applicable</td>
<td rowspan="2">Not applicable</td>
</tr>
<tr>
<td>Billed sales</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="3">An invoice is confirmed, and a decrease in billable hours occurs.</td>
<td>Unbilled sales reversal</td>
<td>Project contract currency</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
</tr>
<tr>
<td>Billed sales – Chargeable for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Billed sales – Non-chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="2">An invoice is corrected to increase the chargeable quantity.</td>
<td>Billed sales – Reversal</td>
<td>Project contract currency</td>
<td rowspan="5">
<ul>
<li>Billed sales reversal for milestone</li>
<li>Change in milestone status from <strong>Invoiced</strong> to <strong>Ready for invoice</strong></li>
</ul>
</td>
<td rowspan="5">Project contract currency</td>
<td rowspan="5">Not applicable</td>
<td rowspan="5">Not applicable</td>
</tr>
<tr>
<td>Billed sales</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="3">An invoice is corrected to decrease the chargeable quantity.</td>
<td>Billed sales – Reversal</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Billed sales for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Unbilled sales – Chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
</tbody>
</table>

### The resource belongs to an organizational unit that differs from the project's contracting unit

<table>
<thead>
<tr>
<th rowspan="3">Event</th>
<th colspan="4">Billable or sold project</th>
<th rowspan="3">Project in the presales stage</th>
<th rowspan="3">Internal project</th>
</tr>
<tr>
<th colspan="2">Time and materials</th>
<th colspan="2">Fixed price</th>
</tr>
<tr>
<th>Actuals</th>
<th>Transaction currency</th>
<th>Fixed price</th>
<th>Transaction currency</th>
</tr>
</thead>
<tbody>
<tr>
<td>A time entry is created.</td>
<td colspan="6">No activity in the Actuals entity</td>
</tr>
<tr>
<td>A time entry is submitted.</td>
<td colspan="6">No activity in the Actuals entity</td>
</tr>
<tr>
<td rowspan="4">Time is approved, and no change to or increase in billable hours occurs during approval.</td>
<td>Cost actual</td>
<td>Contracting unit currency</td>
<td rowspan="4">Cost actual</td>
<td rowspan="4">Contracting unit currency</td>
<td rowspan="4">Cost actual</td>
<td rowspan="4">Cost actual</td>
</tr>
<tr>
<td>Unbilled sales actual – Chargeable</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Resourcing unit cost</td>
<td>Resourcing unit currency</td>
</tr>
<tr>
<td>Interorganizational sales</td>
<td>Contracting unit currency</td>
</tr>
<tr>
<td rowspan="5">Time is approved, and a decrease in billable hours occurs during approval.</td>
<td>Cost actual</td>
<td>Contracting unit currency</td>
<td rowspan="5">Cost actual</td>
<td rowspan="5">Contracting unit currency</td>
<td rowspan="5">Cost actual</td>
<td rowspan="5">Cost actual</td>
</tr>
<tr>
<td>Resourcing unit cost</td>
<td>Resourcing unit currency</td>
</tr>
<tr>
<td>Interorganizational sales</td>
<td>Contracting unit currency</td>
</tr>
<tr>
<td>Unbilled sales actual – Chargeable for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Unbilled sales actual – Non-chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="2">An invoice is confirmed, and no change to or increase in billable hours occurs.</td>
<td>Unbilled sales reversal</td>
<td>Project contract currency</td>
<td rowspan="2">Billed sales for milestone</td>
<td rowspan="2">Project contract currency</td>
<td rowspan="2">Not applicable</td>
<td rowspan="2">Not applicable</td>
</tr>
<tr>
<td>Billed sales</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="3">An invoice is confirmed, and a decrease in billable hours occurs.</td>
<td>Unbilled sales reversal</td>
<td>Project contract currency</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
<td rowspan="3">Not applicable</td>
</tr>
<tr>
<td>Billed sales – Chargeable for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Billed sales – Non-chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="2">An invoice is corrected to increase the chargeable quantity.</td>
<td>Billed sales – Reversal</td>
<td>Project contract currency</td>
<td rowspan="5">
<ul>
<li>Billed sales reversal for milestone</li>
<li>Change in milestone status from <strong>Invoiced</strong> to <strong>Ready for invoice</strong></li>
</ul>
</td>
<td rowspan="5">Project contract currency</td>
<td rowspan="5">Not applicable</td>
<td rowspan="5">Not applicable</td>
</tr>
<tr>
<td>Billed sales</td>
<td>Project contract currency</td>
</tr>
<tr>
<td rowspan="3">An invoice is corrected to decrease the chargeable quantity.</td>
<td>Billed sales – Reversal</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Billed sales for the new quantity</td>
<td>Project contract currency</td>
</tr>
<tr>
<td>Unbilled sales – Chargeable for the difference</td>
<td>Project contract currency</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
