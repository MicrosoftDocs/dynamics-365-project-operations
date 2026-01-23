---
title: Add new invoice line details to a draft project-based proforma invoice
description: Learn how to add new invoice line details to an existing proforma project-based invoice that is in Draft status.
author: suvaidya
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---
# Add new invoice line details to a draft project-based proforma invoice

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

[!INCLUDE[banner](../includes/banner.md)]

You can create transactions for time, expense, and material usage directly on a draft invoice. This feature streamlines the invoicing process and helps ensure timely and accurate billing. It provides significant financial and administrative benefits to project-oriented companies by enhancing operational efficiency and accelerating cash flow.

This feature is available in Project Operations Core deployments of Microsoft Dynamics 365 Project Operations. In Update Release (UR) 54, it's also being extended to Project Operations Integrated with ERP based scenarios deployments.

> [!NOTE]
> Enable the feature at **Settings** \> **Parameters** \> **Feature control** \> **Enable improvements in invoice creation**.
>
> After you enable the feature, you can't disable it.

## Create new invoice line details on a draft proforma invoice

To create new invoice line details on a draft proforma invoice, follow these steps:

1. On the invoice line page, select **New** to create an invoice line detail of the **Time**, **Expense**, **Material**, or **Fee** transaction class.
1. Update the invoice line detail with a price, quantity, billing type, external description, or description.
1. Save the invoice line detail.

## The impact of newly created invoice line details on actuals

Invoice line details that you add manually to an invoice don't have backing actuals. The system adds backing actuals for these invoice line details only when you confirm the invoice.

- **On a time and material contract line**: When you confirm the invoice, the system creates an unbilled sales actual, an unbilled sales reversal actual, and a billed sales actual for the amount that you specify in the manually added invoice line detail.
- **On a fixed price Contract line**: When you confirm the invoice, the system creates a billed sales actual for the amount that you specify in the manually added invoice line detail.

For more information about how different invoicing events affect actuals, see [Actuals impact in a time and materials engagement](../actuals/ActualsonTM.md) and [Actuals impact in a fixed price engagement](../actuals/ActualonFP.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
