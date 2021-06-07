---
title: Correct accounting on draft project invoice proposals
description: This topic provides the details about adjusting accounting related information on draft invoice proposal with Project Operations for resource/ non-stocked based scenarios.
author: sigitac
ms.date: 06/07/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Correct accounting on draft project invoice proposals

_**Applies To:** Project Operations for resource/non-stocked based scenarios_
Project invoice operational details are maintained by project manager in proforma invoice. This includes decisions on which hours, expenses, materials, or milestones need invoicing, what are the rates, advance and retainer amounts application and similar. After confirming original proforma invoice, user can adjust this detail by creating [corrective proforma invoice](https://docs.microsoft.com/en-us/dynamics365/project-operations/proforma-invoicing/corrective-invoices) and confirming it.

Project invoice accounting details are maintained in customer facing invoice document. This includes sales tax calculation and financial dimensions applied to the invoice. This article outlines the details how this information can be adjusted on draft project invoice proposal

## Adjusting sales tax

Billing sales tax group and item sales tax group defaults can be adjusted directly on the invoice proposal document, by clicking Edit button and selecting desired values in fields Sales tax group and Item sales tax group on each project invoice proposal line.

## Adjusting financial dimensions

Financial dimensions cannot be edited directly on project invoice proposal line. User must perform the following actions to adjust financial dimensions on project invoice proposal:

1. Delete project invoice proposal lines by clicking **Delete all** lines button. Note that this button is available only after system administrator enables the feature **Delete invoice proposal lines when using Project Operations for resource based/ non-stocked scenarios** in **Feature management** workspace.
2. Adjust financial dimensions:
  1. **On-account transactions** (billing milestones) financial dimensions can be adjusted in **All projects \&gt; Manage \&gt; On-account transactions** by selecting the milestone that needs adjustment, and editing values in **Financial dimensions** tab.
  2. **Time, expense, and material transactions** financial dimensions can be adjusted by using **Adjust accounting** function in Posted project transactions form.
3. Once financial dimension values are adjusted, run periodic process Import from staging table in **Project Management and Accounting \&gt; Periodic \&gt; Project Operations integration.** Process will recreate project invoice proposal lines using updated financial dimension values and will use these values in project subledger and general ledger when posting project invoice.
