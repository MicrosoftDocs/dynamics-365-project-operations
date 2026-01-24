---
title: Recall previously approved entries
description: This article explains how a project team member can request the recall of previously submitted and approved time, expense, and material usage records, and how a project manager can approve or reject recall requests.
author: suvaidya
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava

---

# Recall previously approved entries

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A project team member who submits a time, expense, or material usage entry can recall that entry after it's approved. The recall process has two main steps:

1. A submitter requests a recall.
1. An approver approves the recall request.

## Request a recall

Follow these steps to request a recall of approved time, expense, or material usage entries.

1. Follow one of these steps, depending on the type of entry that you want to recall:
    - For time entries, go to **Projects** \> **My Work** \> **Time Entry**, and select all the time entries for a specific combination of a project and a task. Alternatively, in the grid, select the individual cells for time on a specific date for a specific project.
    - For expense entries, go to **Projects** \> **My Work** \> **Expenses**, and select the row for the expense entry to recall.
    - For material usage entries, go to **Projects** \> **My Work** \> **Material Usage Log**, and select the row for the material usage entry to recall.
1. Select **Recall**. A confirmation dialog box appears. If the selected time, expense, or material usage entries are already approved, you're prompted to enter a reason for the recall.
1. Enter a reason for the recall, and then select **OK** to confirm the operation. The system sends the person who approved the entries a request to approve the recall.

> [!IMPORTANT]
> You can't create a recall request for an approved time, expense, or material usage entry that the system already invoiced to the customer. If you try, you receive a message that states that the time, expense, or material usage entry can't be recalled because the system already invoiced it. In this case, you can request a recall of the entry only if a corrective invoice is used to issue a full credit or refund to the customer on the original invoice.

## Approve or reject a recall request

Follow these steps to approve or reject a recall request.

1. Go to **Projects** \> **My Work** \> **Approvals**.
1. On the **Approvals** list page, change the view to **Recall requests for approval**. A list of submitted recall requests appears.
1. Select one or more entries, and then select either **Approve** or **Reject**.
1. If you select **Approve**, you receive a warning message that explains the impact of the approval. Select **OK** to confirm the operation. The recall request is approved.

    –or–

    If you select **Reject**, the recall request is rejected.

> [!IMPORTANT]
> When a recall is approved, just as when it's requested, the system checks for any invoicing activity on the time, expense, or material usage entries. If an entry was already invoiced, or if it's on a draft invoice, the approver receives an error message that states that the time or expense can't be approved for recall because it was already invoiced. In this case, the approver can approve the recall only if a corrective invoice is used to issue a full credit or refund to the customer on the original invoice.

## Impact of a recall request

When an approval is recalled, there's both operational impact and financial impact.

### Operational impact

If a recall request is approved, the approval record is marked as **Rejected**. The status of the entry changes to either **Returned** or **Rejected**, depending on whether it's a time entry or an expense or material usage entry.

The project team member can view entries, edit and then resubmit entries, or completely delete entries.

If a recall request is rejected, the status of the entry remains **Approved**, and the entry can't be edited by the project team member or the approver for the project.

### Financial impact

If you approve a recall request, the system updates the corresponding actuals for cost and sales in the following manner:

- The system updates the **Adjustment Status** field to **Adjusted**.
- The system updates the **Billing Status** field to **Canceled**.

Next, the system creates reversal entries in the Actuals table. To create reversal entries, the system copies over the field values from the original actuals. The only values that aren't copied over are the quantity values. The system reverses these values. The system creates reversed actuals for both **Cost** and **Unbilled Sales** actuals. The system sets the **Adjustment Status** field on the reversed actuals to **Unadjustable**, and sets the **Billing status** field to **Canceled**. Because of these changes, the recorded spending and the revenue backlog on the project no longer account for the amounts that these actuals represent.

If you reject a recall request, there's no financial impact on the project.

## Changes to time entry records

The following illustration shows the changes that occur for approved time entries and the corresponding approval records when you recall them.

:::image type="content" source="media/TimeEntryStateTransitions.png" alt-text="Screenshot of time entry state transitions.":::

## Changes to expense and material usage entry records

The following illustration shows the changes that occur for approved expense and material usage entries and the corresponding approval records when you recall them.

:::image type="content" source="media/ExpenseEntryStateTransitions.png" alt-text="Screenshot of expense entry state transitions.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
