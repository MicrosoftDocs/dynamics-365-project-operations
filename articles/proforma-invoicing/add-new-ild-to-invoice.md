---
title: Add new invoice line details to a draft project-based proforma invoice
description: Learn how to add new invoice line details to an existing proforma project-based invoice that is in Draft status.
author: suvaidya
ms.date: 02/14/2025
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Add new invoice line details to a draft project-based proforma invoice

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

[!INCLUDE[banner](../includes/banner.md)]

Transactions for time, expense, and material usage can be created directly on a draft invoice. This feature streamlines the invoicing process and helps ensure timely and accurate billing. It provides significant financial and administrative benefits to project-oriented companies by enhancing operational efficiency and accelerating cash flow.

The feature is available in lite deployments of Microsoft Dynamics 365 Project Operations. In Update Release (UR) 54, it's also being extended to resource/non-stocked based scenarios deployments.

> [!NOTE]
> The feature can be enabled at **Settings** \> **Parameters** \> **Feature control** \> **Enable improvements in invoice creation**.
>
> After the feature is enabled, it can't be disabled.

## Create new invoice line details on a draft proforma invoice

To create new invoice line details on a draft proforma invoice, follow these steps.

1. On the invoice line page, select **New** to create an invoice line detail of the **Time**, **Expense**, **Material**, or **Fee** transaction class.
1. Update the invoice line detail with a price, quantity, billing type, external description, or description.
1. Save the invoice line detail.

## The impact of newly created invoice line details on actuals

Invoice line details that are manually added to an invoice don't have backing actuals. Backing actuals for these invoice line details are added only when the invoice is confirmed.

- **On a time and material contract line**: Confirmation of the invoice creates an unbilled sales actual, unbilled sales reversal actual, and billed sales actual for the amount that was specified in the manually added invoice line detail.
- **On a fixed price Contract line**: Confirmation of the invoice creates a billed sales actual for the amount that was specified in the manually added invoice line detail.

Learn more about how different invoicing events can affect actuals in [Actuals impact in a time and materials engagement](../actuals/ActualsonTM.md) and [Actuals impact in a fixed price engagement](../actuals/ActualonFP.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
