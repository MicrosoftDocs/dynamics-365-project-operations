---
title: Cancel the approval of previously approved entries
description: This article explains how a project manager can cancel the approval of previously approved time, expense, or material usage entries.
author: suvaidya
ms.date: 06/10/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava

---

# Cancel the approval of previously approved entries

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A project manager or approver who has previously approved time, expense, or material usage entries can cancel their approval of those entries. 

Follow these steps to cancel the approval of a previously approved time, expense, or material usage entry.

1. Go to **Projects** \> **My Work** \> **Approvals**.
2. The **Approvals** list page shows all time entries that are awaiting approval. Change the view to **My past approvals**.
3. Select the time, expense, or material approvals to cancel. Then, on the Action Pane, select **Cancel Approval**.
4. In the confirmation message box that appears, select **OK** to confirm the operation.

> [!IMPORTANT]
> You can't cancel the approval of a previously approved time, expense, and material usage entry that has already been invoiced to the customer. If you try, you receive a message that states that the approval can't be canceled because it was already invoiced. In this case, you can cancel the approval only if a corrective invoice is used to issue a full credit or refund to the customer on the original invoice.

## Impact of canceling the approval of a previously approved entry

When an approval is canceled, there is both operational impact and financial impact.

### Operational impact

If the approval of an entry is canceled, the approval record is marked as **Submitted**. The status of the entry is changed to **Submitted**. In this stage, a project team member can recall the entry without submitting a recall request.

The approver can change the **Billable quantity** and **Billing type** values, and then approve the entry one more time.

### Financial impact

If the approval of an entry is canceled, the corresponding actuals for cost and sales are updated in the following manner:

- The **Adjustment Status** field is updated to **Adjusted**.
- The **Billing Status** field is updated to **Canceled**.

Next, reversal entries are created in the Actuals table. To create reversal entries, the system copies over the field values from the original actuals. The only values that aren't copied over are the quantity values. These values are reversed instead. Reversed actuals are created for both **Cost** and **Unbilled Sales** actuals. The **Adjustment Status** field on the reversed actuals is set to **Unadjustable**, and the **Billing status** field is set to **Canceled**. Because of these changes, the recorded spending and the revenue backlog on the project will no longer account for the amounts that these actuals represent.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
