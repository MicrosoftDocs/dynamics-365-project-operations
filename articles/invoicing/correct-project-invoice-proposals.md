---
title: Correct the accounting on draft project invoice proposals
description: Learn how to adjust accounting details like sales tax and financial dimensions on draft project invoice proposals to ensure accurate customer-facing invoices.
author: ryansandness
ms.author: ryansandness
ms.date: 02/05/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Correct the accounting on draft project invoice proposals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

The project manager maintains *operational details* for project invoices on a pro forma invoice. These details include the decision about the hours, expenses, materials, or milestones that must be invoiced, the rates, and the application of advance and retainer amounts. After you confirm the original pro forma invoice, you can adjust the operational details by creating and confirming a [corrective pro forma invoice](../proforma-invoicing/corrective-invoices.md).

The accounting team maintains *accounting details* for project invoices in a customer-facing invoice document. These details include the sales tax calculation and the financial dimensions that are applied to the invoice. This article provides details about how you can adjust these accounting details on a draft project invoice proposal.

## Adjust sales tax

You can adjust default billing sales tax groups and item sales tax groups directly on the invoice proposal document. To adjust these groups, select **Edit**. Then, on each project invoice proposal line, enter a new value in the **Sales tax group** or **Item sales tax group** field.

## Adjust financial dimensions

### Header dimensions

By default, the system derives invoice financial dimensions from the unbilled project transaction records that the invoice includes. However, system settings let you use financial dimensions on the header of project invoice proposals to post customer balances. To enable this functionality, select **Allow updates to project dimensions for accounts receivable** on the **Financials** tab of the **Project management and accounting parameters** page.

You can edit financial dimensions on invoice headers before an invoice is posted. On the **Project invoice proposal** page, switch to the **Header** view, and then edit values on the **Financial dimensions** tab.

The **Header** view is available only after the system administrator enables the **Use Project invoice proposal and invoice journal forms with the Header and Lines view** feature in the **Feature management** workspace. This feature requires Finance update 10.0.25 or later.

### Line dimensions

You can't edit financial dimensions directly on a project invoice proposal line. Instead, follow these steps to adjust financial dimensions on a project invoice proposal.

1. On the project invoice proposal, select **Delete all** to remove the project invoice proposal lines.

    The **Delete all** button is available only after the system administrator enables the **Delete invoice proposal lines when using Project Operations for resource based/ non-stocked scenarios** feature in the **Feature management** workspace.

1. Adjust the financial dimensions:

    - **On-account transactions (billing milestones):** Go to **All projects** \> **Manage** \> **On-account transactions**, and select the milestone that requires adjustment. Then, on the **Financial dimensions** tab, update the values as required.
    - **Time, expense, and material transactions:** On the **Posted project transactions** page, select **Adjust accounting** to update the financial dimensions.

1. After you finish adjusting the financial dimension values, go to **Project management and accounting** \> **Periodic** \> **Project Operations integration**, and select **Import from staging table** to run the periodic process. That process uses the updated financial dimension values to re-create the project invoice proposal lines. The updated values are then used in the project subledger and general ledger when the project invoice is posted.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
