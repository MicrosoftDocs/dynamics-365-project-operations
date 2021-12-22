---
title: Correct the accounting on draft project invoice proposals
description: This topic explains how to adjust accounting-related information on a draft invoice proposal.
author: sigitac
ms.date: 06/07/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Correct the accounting on draft project invoice proposals

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

*Operational details* for project invoices are maintained by the project manager on a pro forma invoice. These details include the decision about the hours, expenses, materials, or milestones that must be invoiced, the rates, and the application of advance and retainer amounts. After you confirm the original pro forma invoice, you can adjust the operational details by creating and confirming a [corrective pro forma invoice](../proforma-invoicing/corrective-invoices.md).

*Accounting details* for project invoices are maintained in a customer-facing invoice document. These details include the sales tax calculation and the financial dimensions that are applied to the invoice. This topic provides details about how these accounting details can be adjusted on a draft project invoice proposal.

## Adjust sales tax

Default billing sales tax groups and item sales tax groups can be adjusted directly on the invoice proposal document. To adjust these groups, select **Edit**, and then, on each project invoice proposal line, enter a new value in the **Sales tax group** or **Item sales tax group** field.

## Adjust financial dimensions

### Header dimensions
By default, invoice financial dimensions are derived from the unbilled project transaction records being invoiced. However, system settings allow using project invoice proposal header financial dimensions for customer balance posting. Parameter can be turned on in Project management and accounting parameters, Financials tab by selecting **Allow updates to project dimensions for accounts receivable**.
Invoice header financial dimensions can be edited before posting the invoice in the Project invoice proposal form by opening Header view and editing values in the Financial dimensions tab. 

    > The **Header view** is available only after the system administrator enables the **Use Project invoice proposal and invoice journal forms with the Header and Lines view** feature in the **Feature management** workspace. Feature requires Finance and Operations update 10.0.25 or higher.
    
### Line dimensions
Financial dimensions can't be edited directly on a project invoice proposal line. Instead, follow these steps to adjust financial dimensions on a project invoice proposal.

1. On the project invoice proposal, select **Delete all** to remove the project invoice proposal lines.

    > The **Delete all** button is available only after the system administrator enables the **Delete invoice proposal lines when using Project Operations for resource based/ non-stocked scenarios** feature in the **Feature management** workspace.

2. Adjust the financial dimensions:

    - **On-account transactions (billing milestones):** Go to **All projects** \> **Manage** \> **On-account transactions**, and select the milestone that requires adjustment. Then, on the **Financial dimensions** tab, update the values as required.
    - **Time, expense, and material transactions:** On the **Posted project transactions** page, select **Adjust accounting** to update the financial dimensions.

3. After you've finished adjusting the financial dimension values, go to **Project management and accounting** \> **Periodic** \> **Project Operations integration**, and select **Import from staging table** to run the periodic process. That process uses the updated financial dimension values to re-create the project invoice proposal lines. The updated values are then used in the project subledger and general ledger when the project invoice is posted.
