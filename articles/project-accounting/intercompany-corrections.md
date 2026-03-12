---
title: Correct intercompany posted transactions (Preview)
description: This article provides information about intercompany corrections for project accounting.
author: ryansandness
ms.author: ryansandness
ms.date: 03/12/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Correct intercompany posted transactions (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations for manufacturing-based scenarios_

An intercompany transaction occurs when a worker is employed by one legal entity but performs work for a project owned by another legal entity. For example, a worker employed by Contoso US might submit timesheets for work performed on a project sold and managed by Contoso Europe. In this scenario, Contoso US acts as the lending legal entity, while Contoso Europe is the borrowing legal entity. Because the timesheet spans two legal entities, pricing-related corrections from the lending company are more complex than corrections for non-intercompany timesheets.

This feature addresses this complexity by creating a reversal copy of the original line at the original price, along with a new line that you can edit and post with corrected values. This process ensures a strict 1:1 original to reversal and guarantees that updated values flow consistently to both the lending and borrowing legal entities. Timesheets are currently the only supported document type for corrections. The feature requires no setup for delegation of submitting documents on behalf of another user for users submitting corrections.

Enable the new functionality from the **Feature management** workspace by enabling the **Enable posted intercompany project transactions correction** feature.

You can access the feature by using the **Intercompany posted transactions** page, which is available at **Project Management and accounting** \> **Transactions**.

Tooltips provide more information about related documents when you hover over checkboxes.

## Enhancements to related areas

1. Within Timesheets, you see new columns for **Reversal** and **Original timesheet number** that are only visible when you go to timesheets through the intercompany processes.

1. For the **Create intercompany invoice** form, improvements include:

- When you create a new invoice, the form is wider and you can see more columns.
- There's a new **Reversal** column to show if the transaction came from a correction.
- New columns for **Original invoice posted** and **Original transaction ID** give details on the original transaction that was reversed.

1. Within the **Intercompany customer invoice** form, selecting **original document** now takes you back to **Intercompany posted transactions** which gives you more details before you select the timesheet.

1. For the **Pending vendor invoice** form, improvements include:

- The line details on the **Project** tab now show whether the transaction came from the project intercompany process or not.
- New fields list the original transaction origin (timesheet, expense, and so on) as well as the original transaction ID, which takes you back to **Intercompany posted transactions**.
- A warning says you shouldn't make changes to a reversal entry.

1. For the **Posted project transactions** form, improvements include:

- A new column shows if the transaction is intercompany.
- You can go to intercompany posted transactions to view or correct transactions from this form.

1. When you perform **Adjustments** on intercompany transactions, you see a warning that you might want to use corrections instead.

## Corrections process flow

The following steps show the typical flow for intercompany corrections.

1. Open the **Intercompany posted transactions** page. This page shows both incoming and outgoing intercompany project transactions.
1. Select the appropriate date filters. By default, the prior 30 days are shown.
1. Scan for any values in the **Alert** column. You receive an indication for scenarios where either the cost price is zero, the sales price is zero, or the current date effective cost or sales price is different than the posted price.
1. Select the lines that need correction. In the ribbon, select **Correct transactions**. The transactions set **Correction status** to **Corrected** and the **Corrected document number** is populated with the new timesheet number.
1. Select the **Corrected document number** or the message in the infolog to **View timesheet**. You go to the document and see a line for the reversal as well as the new line for the corrected entry.
1. Within the timesheet, you can't make changes for the negative transaction. For the new line, you can delete it to post a reversal only or edit it to post to a different day or project. Or sales prices can be updated before posting the new timesheet to have the timesheet post with updated pricing.
1. Create an intercompany customer invoice for the correction. You can't create the reversal customer invoice until you post the original customer invoice.
1. Post the pending vendor invoice for the intercompany transaction.
1. The correction transaction now flows through to the project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]