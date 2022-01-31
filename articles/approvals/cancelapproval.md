---
title: Cancel approval on approved entries
description: This topic provides information on how a project manager can cancel approval on previously approved time, expense, material usage entries.
author: rumant
ms.date: 01/31/2021
ms.topic: overview
ms.reviewer: tonyafehr
ms.author: rumant

---


# Cancel approval on previously approved entries


_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

A project manager or approver that has previously approved a time, expense or material usage entry can cancel thier approval on that entry. Follow these steps to cancel the approval on a previously approved time, expense or material usage entry.

1. Go to **Projects** \> **My Work** \> **Approvals**.
2. The approvals view will open showing all Time entries awaiting approval. Change the view to **"My past approvals"** 
3. Select the specific time, expense or material approvals that you wish to cancel your approval on. Select **Cancel Approval** from the ribbon actions. A confirmation dialog box appears. 
4. Select **OK** to confirm the operation. 

> [!NOTE]
> Although you can cancel the approval on a previously approved time, expense and material usage entries, if the entry has already been invoiced to the customer, the approval cannot be canceled. The user attempting to cancel thier approval will receive a message that states that the approval cannot be canceled because it was already invoiced. Cancel approval will become possible again if a full credit or refund is issued to the customer on the original invoice using a corrective invoice.


## Impact of canceling the approval on a previously approved entry

When an approval is canceled, there is both operational impact and financial impact.

### Operational impact

If the approval is canceled, the approval record is marked as **Submitted**. The status of the entry is changed to  **Submitted**. In this stage, the project team member can recall the entry without submitting a recall request.

The approver may change **Billable quantity** and **Billing type** values and approve the entry one more time.

### Financial impact

When the approval on an entry is canceled, the corresponding actuals for cost and sales are updated in the following manner:

- The **Adjustment Status** field is updated to **Adjusted**.
- The **Billing Status** field is updated to **Canceled**.

Next, reversal entries are created in the Actuals table. To create reversal entries, the system copies over the field values from the original actuals. The only values that aren't copied over are the quantity values. These values are reversed instead. Reversed actuals are created for both **Cost** and **Unbilled Sales** actuals. The **Adjustment Status** field on the reversed actuals is set to **Unadjustable**, and the **Billing status** field is set to **Canceled**. Because of these changes, the recorded spending and the revenue backlog on the project will no longer account for the amounts that these actuals represent.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
