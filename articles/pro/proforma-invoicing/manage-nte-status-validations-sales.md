---
title: Manage not-to-exceed status and validations 
description: This article provides information about the not-to-exceed limit checks performed in Project Operations. 
author: poojafandan
ms.date: 06/07/2024
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

When a time, expense, or material usage entry is submitted, an approval record is created. If the approval is chargeable and maps to a time and material contract line, the system completes a not-to-exceed validation check at the following levels:

  - Check against the limit set up for the customer on the project contract line
  - Check against the limit set up on the contract line
  - Check against the limit set up for the customer
  - Check against the limit set up on the contract

The checks at each level involve ensuring that the amount of sales value on this approval will not violate the not-to-exceed limit at that level after accounting for the amount of billing backlog already recorded, and the amount invoiced to date at that level.

If the check passes, the approval is given a validation status of **Success**.

If the check fails, the approval is given a validation status of **Failed**. The not-to-exceed validation detail will inform the user at which level the validation failed.

When the submitted time, expense, or material usage entry is considered non-chargeable, the not-to-exceed validation status is set to **Not Applicable** with the validation detail equal to **Not applicable**.

## Not-to-exceed on unbilled sales actuals

When a time, expense, or material usage entry is approved, cost and unbilled sales actuals records are created. If the unbilled sales actual being created is chargeable and maps to a time and material contract line, the application performs a not-to-exceed validation check at the following levels:

  - Check against the limit set up for the customer of the project contract line
  - Check against the limit set up on the contract line
  - Check against the limit set up for the customer
  - Check against the limit set up on the contract

The checks at each level ensure that the amount of sales value on the actual will not violate the not-to-exceed limit at that level after accounting for the amount of billing backlog already recorded, and the amount invoiced to date at that level.

If the check passes, the unbilled sales actual is given a not-to-exceed status of **Committed**.

If the check fails, the unbilled sales actual is given a not-to-exceed status of **Failed**. The validation detail informs the user at which level the validation failed.

When the unbilled sales actual is considered non-chargeable or complimentary, if there is no not-to-exceed limit setup at any of the four levels, or if the actual being created is Cost, Retainer, Resourcing Unit, or Inter-organization Sales, the **Not-to-Exceed Status** and **Not-to-Exceed Validation Detail** fields must be set to **Not Applicable**.

## Reset the not-to-exceed status

You can perform a bulk reset of the not-to-exceed status. Project managers can adjust the not-to-exceed validation to prioritize invoicing of one particular body of work, time, expense, or material usage over others that are already committed from the available not-to-exceed amount.

After the not-to-exceed status is reset on unbilled sales actuals, the committed amount is reduced. The Project manager can select another body of work, time, expense, or material usage entry that previously failed the not-to-exceed validation and reevaluate. With the reduction in the committed amount, these actuals now pass the validation which helps the Project manager exert greater influence and control over the invoiceable transactions for that period.

To reset the not-to-exceed status, select one or more actuals from the **Time and Material Billing Backlog** or **Actuals** view, and then select **Reset Not-to-Exceed Status**.

The not-to-exceed status is reset to **Not Evaluated** on all of the relevant selected actuals. Actuals that have their not-to-exceed status reset are unbilled sales actuals that aren't already invoiced, not on a draft invoice, and are marked as chargeable. Any other selected actuals are ignored.

## Reevaluate not-to-exceed status

You can perform a bulk re-evaluation of the not-to-exceed status. Re-evaluation of the not-to-exceed status is useful when:

  - There was a renegotiation of not-to-exceed limits with the customer and actuals will need to be reevaluated.
  - The Project manager wants to fine-tune the invoicing of unbilled sales backlog by prioritizing one body of work over another.

To reevaluate the not-to-exceed status, select one or more actuals from the **Time and Material Billing Backlog** or **Actuals** view, and select **Reevaluate Not-to-Exceed Status**.

All of the relevant selected actuals with a not-to-exceed limit will be evaluated against the not-to-exceed limit setup. Actuals that are relevant for re-evaluating the not-to-exceed status are unbilled sales actuals that are not invoiced, not on a draft invoice, and are marked as chargeable. Any other select actuals selected.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
