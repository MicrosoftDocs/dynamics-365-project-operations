---
title: Verification of vendor invoices with approved actuals
description: Learn how to verify vendor invoices with approved actuals in Microsoft Dynamics 365 Project Operations. Streamline invoice validation with step-by-step guidance.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---


# Verification of vendor invoices with approved actuals

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations lets project managers verify vendor invoice lines in the following ways:

- Use the **Verification status** field on the vendor invoice lines.
- If the vendor invoice lines reference a subcontract line, link cost actuals from subcontractor activity to those vendor invoice lines. You create the link by matching cost actuals to the vendor invoice lines.

    > [!NOTE]
    > Although you can track verification status for vendor invoice lines that don't reference a subcontract, you can't link cost actuals to those vendor invoice lines.

## Verification status

The **Verification status** field on a vendor invoice line indicates the status of the verification. The following statuses are supported:

1. Not started
1. In progress
1. Complete

You can edit vendor invoice lines that have a verification status of **Not started**.

You can't edit vendor invoice lines that have a verification status of **In progress**. For a vendor invoice line that references a subcontract, the verification status automatically changes to **In progress** as soon as you match the first cost actual to the vendor invoice line.

You can't edit vendor invoice lines that have a verification status of **Complete**. When all the lines on a vendor invoice have this verification status, you can confirm the vendor invoice.

## Match cost actuals to vendor invoice lines

Matching cost actuals helps you verify a vendor invoice line. To match cost actuals to a vendor invoice line, follow these steps:

1. Open the vendor invoice line, and select the **Unmatched cost actuals** tab. A grid shows a list of cost actuals that reference the same subcontract line as the vendor invoice line.
1. Select one or more of the cost actuals, and then select **Match** on the toolbar above the grid. The system validates that the selected cost actuals can be matched. After the validation passes, the cost actuals link to the vendor invoice line.

### Validation criteria that link cost actuals to vendor invoice lines

During the matching process, you can link a cost actual to a vendor invoice line only if both the following conditions are met:

- The **Adjustment status** field is blank for every selected cost actual. In other words, the cost actuals aren't replaced by other cost actuals during a recall, approval cancellation, or correction journal process.
- The values of the following fields match between the vendor invoice line and the selected cost actual. If you don't set any field on the vendor invoice line, it's not considered for matching.

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

Unmatching cost actuals can also help with the verification process on a vendor invoice by enabling you to remove previously established links. You can unmatch cost actuals only from vendor invoice lines that have a verification status of **In progress**. To unmatch cost actuals from a vendor invoice line, follow these steps:

1. Open the vendor invoice line, and select the **Matched cost actuals** tab. A grid shows a list of cost actuals that reference the vendor invoice line.
1. Select one or more of the cost actuals, and then select **Unmatch** on the toolbar above the grid.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
