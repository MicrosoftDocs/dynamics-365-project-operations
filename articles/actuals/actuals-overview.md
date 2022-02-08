---
# required metadata

title: Actuals 
description: This topic provides information about how to work with actuals in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 04/01/2021
ms.topic: overview
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: tonyafehr
ms.search.scope: 
# ms.tgt_pltfrm: 

ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: rumant
ms.search.validFrom: 2020-10-01
---

# Actuals 

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Actuals represent the reviewed and approved financial and schedule progress on a project. They are created when time, expense, and material usage entries, journal entries, and invoices are approved. You should not edit actuals or delete them from the system. Otherwise, you might adversely affect the financial integrity and any integration with other financial and accounting systems. Instead, Microsoft Dynamics 365 Project Operations lets you correct actuals by creating reversing and replacing actuals at various points in the business process lifecycle of your projects. 

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
