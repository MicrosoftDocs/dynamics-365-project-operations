---
title: Reconcile accrued revenue 
description: Learn how to detect and correct accrued revenue imbalances in Microsoft Dynamics 365 Project Operations.
author: ryansandness
ms.author: ryansandness
ms.reviewer: johnmichalak
ms.search.form:
ms.topic: how-to
ms.date: 08/18/2026
ms.custom:
  - bap-template
---

# Reconcile accrued revenue

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

Use **Accrued revenue reconciliation** to detect and correct accrued revenue, or work in progress (WIP), that isn't fully reversed after invoicing or adjustment activity. Project accountants can investigate affected transactions, create and post auditable reconciliation journals, and verify that any imbalances are corrected. Run this process as part of month-end closing activities or as part of project closure routines to ensure accurate reporting.

WIP imbalances can result from customizations, product defects, or sometimes rounding differences. If you see new imbalances being generated, work with support to help diagnose a root cause for the issue.

## Prerequisites and setup

Before you reconcile accrued revenue, enable the feature, configure access, review the generated number sequences, and understand batch capabilities if you have any significant volume of imbalances.

### Enable the Accrued revenue reconciliation feature

To enable the Accrued revenue reconciliation feature, follow these steps:

1. Go to **System administration** \> **Workspaces** \> **Feature management**.
1. Search for and select **Accrued revenue reconciliation**.
1. Select **Enable now**.

### Configure access

The **Project accountant** security role provides access by default. In **Security configuration**, administrators can assign equivalent access through the **Maintain accrued revenue reconciliation** duty and its privileges: **View accrued revenue reconciliation** for detection and investigation, **Maintain accrued revenue reconciliation journals** for journal creation, and **Post accrued revenue reconciliation journals** for posting.

Grant the access that each user requires:

- For detect-only access, assign the view privilege without the create or post privileges.
- To create corrections, assign the view and journal-maintenance privileges.
- To post corrections, also assign the posting privilege.
- Users who run creation or posting in batch must also have permission to submit and monitor the corresponding batch jobs.

### Review number sequences

The system provisions the following number sequences for each legal entity the first time that you open the parameters page or create or post a correction journal:

- **Accrued revenue reconciliation journal** identifies correction journal headers.
- **Accrued revenue reconciliation voucher** identifies general ledger vouchers created during posting.

Review or override the sequences on **Project management and accounting** > **Setup** > **Project management and accounting parameters**, on the **Number sequences** tab. Confirm that they follow your organization's numbering conventions before posting.

### Configure batch processing

Configure and monitor batch processing before you process large selections. Journals with 1,000 lines or fewer can run synchronously or in batch where journals with more than 1,000 lines must run in batch. Use batch processing even below the threshold when the selected set is large or synchronous processing might time out.

The default batch job names are **Project accrued revenue reconciliation** for journal creation and **Post reconciliation journal** for posting.

## Access the reconciliation form

Access the **Accrued revenue reconciliation** form from **Project management and accounting** > **Inquiries and reports** > **WIP reports** > **Accrued revenue reconciliation**.

## Supported deployment types

The available detection scope depends on the deployment type.

| Deployment type | Detection scope |
|---|---|---|
| **Project Operations for manufacturing-based scenarios** | Invoicing and adjustments |
| **Project Operations Integrated with ERP** | Invoicing only |

> [!IMPORTANT]
> Detection runs separately for each legal entity. If your organization uses multiple legal entities, switch companies and run detection in each one.

## Reconciliation process flow

Use this end-to-end process to detect, investigate, correct, and verify accrued revenue imbalances:

1. **Detect imbalances.** On **Accrued revenue reconciliation**, set **Start date** and **End date** for the period to review. Start with a narrow range. Review detailed results on **Transactions**, then use **Projects** and **Ledger Accounts** to review in summary by project or account. Select **View project transactions** or **View ledger account transactions** to return to the underlying lines.
1. **Investigate any records returned.** On **Transactions**, use **Imbalance in accounting currency** as the net amount that requires correction. Select the **Reversal transaction ID** link and compare the reversal with the original accrued revenue posting. For adjustment-related rows, select **View pre-adjustment transaction** when applicable.
   - **Hour and expense transactions:** The original WIP accrual is posted under the original transaction ID, and the reversal is posted under the reversal transaction ID. Use **Reversal transaction ID** for the reversal and **View pre-adjustment transaction** for the original accrual.
   - **Fee and item transactions:** The original WIP accrual and reversal are both posted under the original transaction ID. Use **View pre-adjustment transaction** to review both postings together.
   - **Invoice-related transactions:** Use **Reversal transaction ID**. 
   For example, if the original transaction posts 5,000 to accrued revenue and the reversal posts -4,500, **Imbalance in accounting currency** shows a 500 imbalance. The correction journal posts the 500 difference.
1. **Create a correction journal.** Select the affected rows on **Transactions**, **Projects**, or **Ledger Accounts**, and then select **Create reconciliation journal**. Choose synchronous or batch processing. Open the journal from the confirmation message or journal list.
1. **Review and post the journal.** Review the header and lines, enter a **Voucher date** in an open accounting period, update **Description** if needed, and verify the offset account and financial dimensions for an asymmetric correction. Select **Post**, confirm the action, and review the voucher numbers and posting status. After partial or full posting, **Voucher date** and **Description** are read-only.
1. **Verify the correction.** Return to **Accrued revenue reconciliation**, apply the same date filters, and review the results. Confirm that corrected transactions no longer appear or that the imbalance amount is reduced when only part of an imbalance was corrected.

## Correction types

A **symmetric** correction applies when the accrued revenue delta and offset delta are mismatched by the same amount. The journal creates a symmetric correction on both sides.

An **asymmetric** correction applies when the accrued revenue and offset amounts differ. The journal corrects the WIP side and balances through an offset account and financial dimensions that you specify.

## Detection views and filters

Use the three tabs to move between detail and summarized balances.

| Tab | Purpose |
| --- | --- |
| **Transactions** | Shows individual imbalanced transaction lines. |
| **Projects** | Summarizes imbalances by project. |
| **Ledger Accounts** | Summarizes imbalances by ledger account. |

The date filter defaults to the last three months. Narrow the range to reduce the result set and improve performance. To cross-check detected amounts against broader project and ledger balances, use the links to the **Project WIP** and **Ledger reconciliation - WIP** reports.

## Prevent future WIP imbalances

Enable the **Apply exchange rates from project subledger feature** in **Feature management** to keep exchange rate handling aligned between the project subledger and general ledger. You can read more about this feature under [project invoicing](../prod-pma/project-invoicing.md#time-and-material-type-projects-with-accrued-revenue).

## Frequently asked questions

### Why does detection show no results?

Receiving no results back might be correct. Confirm that the date range includes the affected period, the issue involves accrued revenue accounts, and that you're in the correct legal entity. If the feature or newly assigned security access still isn't visible, sign out and start a new session so that feature and security caches refresh.

### Can I undo a posted correction journal?

No built-in reversal action is available. Consider testing in a sandbox prior to performing a correction in production.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
