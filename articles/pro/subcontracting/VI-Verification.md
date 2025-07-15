---
title: Verification of vendor invoices with approved actuals
description: This article explains how Microsoft Dynamics 365 Project Operations lets project managers verify vendor invoices with the actuals that were approved as contractors performed work and recorded time, and the expenses and materials that were used by project team members.
author: rumant
ms.date: 12/15/2023
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---


# Verification of vendor invoices with approved actuals

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP , Project Operations Core_

Microsoft Dynamics 365 Project Operations lets project managers verify vendor invoice lines in the following ways:

- Use the **Verification status** field on the vendor invoice lines.
- If the vendor invoice lines reference a subcontract line, link cost actuals from subcontractor activity to those vendor invoice lines. The link is created by matching cost actuals to the vendor invoice lines.

    > [!NOTE]
    > Although verification status can be tracked for vendor invoice lines that don't reference a subcontract, cost actuals can't be linked to those vendor invoice lines.

## Verification status

The **Verification status** field on a vendor invoice line indicates that status of the verification. The following statuses are supported:

1. Not started
2. In progress
3. Complete

Vendor invoice lines that have a verification status of **Not started** can be edited.

Vendor invoice lines that have a verification status of **In progress** can no longer be edited. For a vendor invoice line that references a subcontract, the verification status is automatically set to **In progress** as soon as the first cost actual is matched to the vendor invoice line.

Vendor invoice lines that have a verification status of **Complete** can no longer be edited. When all the lines on a vendor invoice have this verification status, the vendor invoice can be confirmed.

## Match cost actuals to vendor invoice lines

Matching of cost actuals helps with the verification process on a vendor invoice line. To match cost actuals to a vendor invoice line, follow these steps.

1. Open the vendor invoice line, and select the **Unmatched cost actuals** tab. A grid shows a list of cost actuals that reference the same subcontract line as the vendor invoice line.
2. Select one or more of the cost actuals, and then select **Match** on the toolbar above the grid. The system validates that the selected cost actuals can be matched. After the validation is passed, the cost actuals are linked the vendor invoice line.

### Validation criteria that are used to link cost actuals to vendor invoice lines

During the matching process, a link between a cost actual and a vendor invoice line can be established only if both the following conditions are met:

- The **Adjustment status** field for every selected cost actual must be blank. In other words, the cost actuals must not have been replaced by other cost actuals during a recall, approval cancellation, or correction journal process.
- The values of the following fields are matched between the vendor invoice line and the selected cost actual. If any field isn't set on the vendor invoice line, it isn't considered for matching.

    - Project contract
    - Project contract line
    - Transaction class
    - Project
    - Task
    - Resource category
    - Transaction category
    - Product
    - Subcontract line
    - Bookable resource

## Unmatch cost actuals from a vendor invoice line

Unmatching of cost actuals can also help with the verification process on a vendor invoice by enabling previously established links to be removed. Cost actuals can be unmatched only from vendor invoice lines that have a verification status of **In progress**. To unmatch cost actuals from a vendor invoice line, follow these steps.

1. Open the vendor invoice line, and select the **Matched cost actuals** tab. A grid shows a list of cost actuals that reference the vendor invoice line.
2. Select one or more of the cost actuals, and then select **Unmatch** on the toolbar above the grid.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
