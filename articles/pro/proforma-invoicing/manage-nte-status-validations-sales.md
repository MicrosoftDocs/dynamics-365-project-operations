---
title: Manage not-to-exceed status and validations
description: Learn how to manage not-to-exceed status and validations in Project Operations. Understand limit checks, validation statuses, and how to reset or reevaluate them.
author: poojafandan
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Manage not-to-exceed status and validations

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

## Not-to-exceed on approvals

When you submit a time, expense, or material usage entry, the system creates an approval record. If the approval is chargeable and maps to a time and material contract line, the system completes a not-to-exceed validation check at the following levels:

- Check against the limit set up for the customer on the project contract line
- Check against the limit set up on the contract line
- Check against the limit set up for the customer
- Check against the limit set up on the contract

The checks at each level involve ensuring that the amount of sales value on this approval doesn't violate the not-to-exceed limit at that level after accounting for the amount of billing backlog already recorded, and the amount invoiced to date at that level.

If the check passes, the system gives the approval a validation status of **Success**.

If the check fails, the system gives the approval a validation status of **Failed**. The not-to-exceed validation detail informs the user at which level the validation failed.

When the submitted time, expense, or material usage entry is nonchargeable, the system sets the not-to-exceed validation status to **Not Applicable** with the validation detail equal to **Not applicable**.

## Not-to-exceed on unbilled sales actuals

When you approve a time, expense, or material usage entry, the system creates cost and unbilled sales actuals records. If the unbilled sales actual you're creating is chargeable and maps to a time and material contract line, the application performs a not-to-exceed validation check at the following levels:

- Check against the limit set up for the customer of the project contract line
- Check against the limit set up on the contract line
- Check against the limit set up for the customer
- Check against the limit set up on the contract

The checks at each level ensure that the amount of sales value on the actual doesn't violate the not-to-exceed limit at that level after accounting for the amount of billing backlog already recorded, and the amount invoiced to date at that level.

If the check passes, the unbilled sales actual gets a not-to-exceed status of **Committed**.

If the check fails, the unbilled sales actual gets a not-to-exceed status of **Failed**. The validation detail informs the user at which level the validation failed.

When the unbilled sales actual is nonchargeable or complimentary, if there's no not-to-exceed limit set up at any of the four levels, or if the actual being created is Cost, Retainer, Resourcing Unit, or Inter-organization Sales, set the **Not-to-Exceed Status** and **Not-to-Exceed Validation Detail** fields to **Not Applicable**.

## Reset the not-to-exceed status

You can bulk reset the not-to-exceed status. Project managers can adjust the not-to-exceed validation to prioritize invoicing of one particular body of work, time, expense, or material usage over others that are already committed from the available not-to-exceed amount.

After the not-to-exceed status is reset on unbilled sales actuals, the committed amount is reduced. The Project manager can select another body of work, time, expense, or material usage entry that previously failed the not-to-exceed validation and reevaluate. With the reduction in the committed amount, these actuals now pass the validation that helps the Project manager exert greater influence and control over the invoiceable transactions for that period.

To reset the not-to-exceed status, select one or more actuals from the **Time and Material Billing Backlog** or **Actuals** view, and then select **Reset Not-to-Exceed Status**.

The not-to-exceed status is reset to **Not Evaluated** on all of the relevant selected actuals. Actuals that have their not-to-exceed status reset are unbilled sales actuals that aren't already invoiced, not on a draft invoice, and are marked as chargeable. The system ignores any other selected actuals.

## Reevaluate not-to-exceed status

You can reevaluate the not-to-exceed status for multiple records at once. Re-evaluating the not-to-exceed status is useful when:

- You renegotiate the not-to-exceed limits with the customer and need to reevaluate actuals.
- The project manager wants to fine-tune the invoicing of unbilled sales backlog by prioritizing one body of work over another.

To reevaluate the not-to-exceed status, select one or more actuals from the **Time and Material Billing Backlog** or **Actuals** view, and select **Reevaluate Not-to-Exceed Status**.

The system evaluates all relevant selected actuals with a not-to-exceed limit against the not-to-exceed limit setup. Actuals that are relevant for re-evaluating the not-to-exceed status are unbilled sales actuals that aren't invoiced, aren't on a draft invoice, and are marked as chargeable. Any other actuals you select aren't relevant.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
