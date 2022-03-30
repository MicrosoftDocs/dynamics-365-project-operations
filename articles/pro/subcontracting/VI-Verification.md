---
title: Verification of vendor invoices with approved actuals
description: This topic explains how Microsoft Dynamics 365 Project Operations allows Project Managers to verify vendor invoices with the actuals that were approved as contractors performed work and recorded time and the expenses and materials used by project team members.
author: rumant
ms.date: 03/30/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---


# Verification of vendor invoices with approved actuals

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing

Project Operations supports verification of vendor invoice lines by project managers by

1. Using the verification status field on the vendor invoice lines
2. For Vendor invoice lines that reference a subcontract line, Project Operations enables linking of cost actuals from subcontractor activity to vendor invoice lines. This is done using the process of matching cost actuals to the vendor invoice line

Please Note: Verification of vendor invoices by matching cost actuals to vendor invoice lines is only available on Vendor invoice lines that reference a subcontract line. Verification status can be tracked for vendor invoice lines that do not reference a subcontract, however, linking cost actuals to vendor invoice lines is not supported.

**Verification status:**

Verification status on the vendor invoice line indicates that status of verification. The following are states supported:

1. Not started
2. In progress
3. Completed

When the vendor invoice line is in Verification status **Not Started** , it is editable.

When the vendor invoice line is in Verification status I **n progress** , it is no longer editable. For vendor invoice lines that reference a subcontract, the verification status is automatically set to **In progress** as soon as the first cost actual is matched to the vendor invoice line

When the vendor invoice line is in Verification status **Complete** , it is no longer editable. When all lines on a vendor invoice are in verification status **Complete** the vendor invoice can be confirmed.

**Matching Cost actuals to a vendor invoice line:**

Matching cost actuals helps with the verification process on a vendor invoice line. To match cost actuals to a vendor invoice line, follow these steps:

1. Open the vendor invoice line and navigate to the **Unmatched Cost Actuals** tab. A list of cost actuals that reference the same subcontract line as the vendor invoice line are shown
2. Select one or more of these cost actuals and click on **Match** from the grid tool bar
3. System will validate that if these cost actuals can be matched and once the validation passes, these cost actuals are linked the vendor invoice line.

Validation criteria used to link cost actuals to vendor invoice lines:

To establish a link between a cost actual and a vendor invoice line during the Match process, the following must all be true:

The selected cost actuals must all have an empty Adjustment status i.e. they should not have been replaced by other cost actuals in a recall, cancel approval or a correction journal process.

The values in the following fields are matched between the vendor invoice line, if filled and the selected cost actual: 1. Project Contract 2. Project Contract line 3. Transaction class 4. Project 5. Task 6. Resource category 7. Transaction category 8. Product 9. Subcontract Line 10. Bookable Resource. If any of these fields is not filled on the vendor invoice line, then that field is not considered for matching.

**Unmatching Cost actuals to a vendor invoice line:**

Unmatching cost actuals also helps with the verification process on a vendor invoice line by allowing the removal of previously established links. Unmatching is only allowed on Vendor invoice lines that in verification status &quot;In progress&quot;. To un-match cost actuals to a vendor invoice line, follow these steps:

1. Open the vendor invoice line and navigate to the M **atched Cost Actuals** tab. A list of cost actuals that reference the vendor invoice line are shown
2. Select one or more of these cost actuals and click on **Unmatch** from the grid tool bar


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
