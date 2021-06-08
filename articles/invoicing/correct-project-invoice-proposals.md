---
title: Correct accounting on draft project invoice proposals
description: This topic provides the details about adjusting accounting related information on a draft invoice proposal.
author: sigitac
ms.date: 06/07/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Correct accounting on draft project invoice proposals

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project invoice operational details are maintained on a proforma invoice by the project manager. This includes the decision of what hours, expenses, materials, or milestones need invoicing, what the rates are, and advance and retainer amounts application. After you confirm the original proforma invoice, you can adjust these details by creating and confirming a [corrective proforma invoice](../proforma-invoicing/corrective-invoices.md).

Project invoice accounting details are maintained in a customer-facing invoice document. This includes sales tax calculation and the financial dimensions applied to the invoice. This topic provides details about how this information can be adjusted on a draft project invoice proposal.

## Adjusting sales tax

Billing sales tax group and item sales tax group defaults can be adjusted directly on the invoice proposal document. To adjust these groups, select **Edit** and then select or enter the new values in the **Sales tax group** or **Item sales tax group** fields on each project invoice proposal line.

## Adjusting financial dimensions

Financial dimensions can't be edited directly on a project invoice proposal line. Instead, complete the following steps to adjust financial dimensions on project invoice proposal.

1.On the project invoice proposal, select **Delete all** to remove the project invoice proposal lines. 

  > [!NOTE]
  > This button is available only after the system administrator enables the feature, **Delete invoice proposal lines when using Project Operations for resource based/ non-stocked scenarios** in the **Feature management** workspace.

2. Adjust the financial dimensions:
  
   - **On-account transactions** (billing milestones): Go to **All projects** > **Manage** > **On-account transactions**, select the milestone that needs adjustment, and on the **Financial dimesions** tab, update the values as necessary.
   - **Time, expense, and material transactions**: On the **Posted project transactions** page, select **Adjust accounting** to update the financial dimensions.

3. After you finish adjusting the financial dimension values, go to **Project management and accounting** > **Periodic** > **Project Operations integration**, and select **Import from staging table** to run the periodic process. The process recreates the project invoice proposal lines using updated financial dimension values. These updated values are used in the project subledger and general ledger when posting the project invoice.
