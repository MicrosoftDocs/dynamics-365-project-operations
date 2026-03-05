---
title: (Preview) Corrections for intercompany posted transactions
description: This article provides information about intercompany corrections for project accounting.
author: ryansandness
ms.author: ryansandness
ms.date: 02/07/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Corrections for intercompany posted transactions

_**Applies To:** Project Operations for manufacturing-based scenarios_

## Overview

An intercompany transaction occurs when a worker is employed by one legal entity but performs work for a project owned by another legal entity. For example, a worker employed by Contoso US may submit timesheets for work performed on a project sold and managed by Contoso Europe. In this scenario, Contoso US acts as the lending legal entity, while Contoso Europe is the borrowing legal entity. Because the timesheet spans two legal entities, any corrections for anything pricing related from the lending company is more complex than a single company timesheet.  

This functionality addresses this complexity by supporting a the creation of a new reversal copy of the original document at the original price as well as a new document that can be edited and posted with corrected values. This ensures a strict 1:1 orgiginal to reversal and guarantees that updated values flow consistently to both the lending and borrowing legal entities. Timesheets are the only supported document for correction currently. No setup for delegation of submitting documents on behalf of another user are required for users submitting corrections.

The new functionality can be enabled from the **Feature management** workspace by enabling the **Enable posted intercompany project transactions correction** feature.

Users can access the feature by using the **Intercompany posted transactions** page that you can access from **Project Management and accounting** \> **Transactions**.

Tooltips have been added in several areas that appear when hovering over checkboxes that give more information about related documents.

## Other enhancements added from the feature

1. For the **Create intercompany invoice** form, improvements include:

- When creating a new invoice, the form has been enhanced to be wider and allow for more columns to be visisble. New columns have been added to indicate in the transaction is a reversal, and if the original invoice has been posted. For the purpose of corrections, the original intercompany invoice needs to be posted before the reversal invoice.
- There is a new **Reversal** colum to indicate if the transaction originated from a correction.
- Clicking **original document** will now take you back to **Intercompany posted transactions** which will give you more details before clicking into the timesheet.

1. For the **Pending vendor invoice** form, improvements include:

- The line details has been enhanced on the **Project** tab to include whether or not the transaction orginated from an intercompany process or not.
- New fields have been added to list the original transaction origin (timesheet, expense, etc) as well as the original transaction ID, which will navigate the user back to **Intercompany posted transactions**.

1. For the **Posted project transactions** form, a new column was added to indicate of the transaction is intercompany or not.

1. When performing adjustments of intercompany transactions, users will be warned that they may want to consider using corrections instead.

## Corrections process flow

The following steps show the typical flow for intercopmany corrections.

1. Open the **Intercompany posted transactions** page. This page shows both incoming and outgoing intercompany project transactions.
1. Select the appropriate date filters. By default, you will be shown the prior 30 days.
1. Scan for any values in the **Alert** column. You will receive an indication for scenarios where either the cost price is zero, the sales price is zero, or the current date effective cost or sales price is different than the posted price.
1. Select the line or lines that need correction. In the ribbon, click to **Correct transactions**. The transactions will set **Correction status** to **Corrected** and the **Corrected document number** will be populated with the new timesheet number.
1. Clicking into the **Corrected document number** will navigate to the document and you will see a line for the reversal as well as the new line for the corrected entry.
1. Within the timesheet, no changes are allowed for the negative transaction. For the new line, it can be deleted to post a reversal only or edited to post to a different day or project. Or sales prices can be updated before posting the new timesheet to have the timesheet post with updated pricing.


