---
title: Cancel the approval of previously approved entries
description: This article explains how a project manager can cancel the approval of previously approved time, expense, or material usage entries.
author: suvaidya
ms.date: 01/23/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava

---

# Cancel the approval of previously approved entries

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A project manager or approver who previously approved time, expense, or material usage entries can cancel their approval of those entries. 

Follow these steps to cancel the approval of a previously approved time, expense, or material usage entry.

1. Go to **Projects** \> **My Work** \> **Approvals**.
1. The **Approvals** list page shows all time entries that are awaiting approval. Change the view to **My past approvals**.
1. Select the time, expense, or material approvals to cancel. Then, on the Action Pane, select **Cancel Approval**.
1. In the confirmation message box that appears, select **OK** to confirm the operation.

> [!IMPORTANT]
> You can't cancel the approval of a previously approved time, expense, and material usage entry that you already invoiced to the customer. If you try, you receive a message that states that the approval can't be canceled because it was already invoiced. In this case, you can cancel the approval only if a corrective invoice is used to issue a full credit or refund to the customer on the original invoice.

## Impact of canceling the approval of a previously approved entry

When you cancel an approval, there's both operational impact and financial impact.

### Operational impact

If you cancel the approval of an entry, the system marks the approval record as **Submitted**. The system changes the status of the entry to **Submitted**. In this stage, a project team member can recall the entry without submitting a recall request.

The approver can change the **Billable quantity** and **Billing type** values, and then approve the entry again.

### Financial impact

If you cancel the approval of an entry, the system updates the corresponding actuals for cost and sales in the following manner:

- The system updates the **Adjustment Status** field to **Adjusted**.
- The system updates the **Billing Status** field to **Canceled**.

Next, the system creates reversal entries in the Actuals table. To create reversal entries, the system copies the field values from the original actuals. The system doesn't copy over the quantity values. Instead, it reverses these values. The system creates reversed actuals for both **Cost** and **Unbilled Sales** actuals. The system sets the **Adjustment Status** field on the reversed actuals to **Unadjustable**, and sets the **Billing status** field to **Canceled**. Because of these changes, the recorded spending and the revenue backlog on the project no longer account for the amounts that these actuals represent.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
