---
title: (Preview) Corrections for intercompany posted transactions
description: This article provides information about intercompany corrections for project accounting.
author: ryansandness
ms.author: ryansandness
ms.date: 03/10/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Corrections for intercompany posted transactions

_**Applies To:** Project Operations for manufacturing-based scenarios_

## Overview

An intercompany transaction occurs when a worker is employed by one legal entity but performs work for a project owned by another legal entity. For example, a worker employed by Contoso US may submit timesheets for work performed on a project sold and managed by Contoso Europe. In this scenario, Contoso US acts as the lending legal entity, while Contoso Europe is the borrowing legal entity. Because the timesheet spans two legal entities, corrections for anything pricing related from the lending company is more complex than a non-intercompany timesheet.  

This feature addresses this complexity by supporting the creation of a new reversal copy of the original line at the original price as well as a new line that can be edited and posted with corrected values. This ensures a strict 1:1 original to reversal and guarantees that updated values flow consistently to both the lending and borrowing legal entities. Timesheets are the only supported document for correction currently. No setup for delegation of submitting documents on behalf of another user are required for users submitting corrections.

The new functionality can be enabled from the **Feature management** workspace by enabling the **Enable posted intercompany project transactions correction** feature.

Users can access the feature by using the **Intercompany posted transactions** page that you can access from **Project Management and accounting** \> **Transactions**.

Tooltips have been added in several areas that appear when hovering over checkboxes that give more information about related documents.

### Enhancements to related areas

1. Within Timesheets, new columns have been added for **Reversal** and **Original timesheet number** that will be only visible when navigating to timesheets through the intercompany proceses.

2. For the **Create intercompany invoice** form, improvements include:

- When creating a new invoice, the form has been enhanced to be wider and allows for more columns to be visible.
- There is a new **Reversal** column to indicate if the transaction originated from a correction.
- There are new columns for **Original invoice posted** and **Original transaction ID** to give details on the original transaction that was reversed.

3. Within the **Intercompany customer invoice** form, clicking **original document** will now take you back to **Intercompany posted transactions** which will give you more details before clicking into the timesheet.

4. For the **Pending vendor invoice** form, improvements include:

- The line details has been enhanced on the **Project** tab to include whether or not the transaction orginated from the project intercompany process or not.
- New fields have been added to list the original transaction origin (timesheet, expense, etc) as well as the original transaction ID, which will navigate the user back to **Intercompany posted transactions**.
- A warning has been added to the pending vendor invoice that one should not make changes to a reversal entry.

5. For the **Posted project transactions** form, improvements include:

- A new column was added to indicate if the transaction is intercompany.
- Users can navigate to intercompany posted transactions to view or correct transactions from this form.

6. When performing **Adjustments** on intercompany transactions, users will be warned that they may want to consider using corrections instead.

## Corrections process flow

The following steps show the typical flow for intercompany corrections.

1. Open the **Intercompany posted transactions** page. This page shows both incoming and outgoing intercompany project transactions.
1. Select the appropriate date filters. By default, you will be shown the prior 30 days.
1. Scan for any values in the **Alert** column. You will receive an indication for scenarios where either the cost price is zero, the sales price is zero, or the current date effective cost or sales price is different than the posted price.
1. Select the line or lines that need correction. In the ribbon, click to **Correct transactions**. The transactions will set **Correction status** to **Corrected** and the **Corrected document number** will be populated with the new timesheet number.
1. Clicking into the **Corrected document number** or the message in the infolog to **View timesheet** will navigate to the document and you will see a line for the reversal as well as the new line for the corrected entry.
1. Within the timesheet, no changes are allowed for the negative transaction. For the new line, it can be deleted to post a reversal only or edited to post to a different day or project. Or sales prices can be updated before posting the new timesheet to have the timesheet post with updated pricing.
1. Create an intercompany customer invoice for the correction. The reversal customer invoice cannot be created until the original customer invoice has been posted.
1. The pending vendor invoice for the intercompany transaction can be posted.
1. The correction transaction will now flow through to the project.
