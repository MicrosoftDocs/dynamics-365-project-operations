---
title: Add new invoice line details to a draft invoice
description: Learn about how to add new invoice line details to an existing proforma project-based invoice in draft status.
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

The ability to create transactions for time, expense, and material usage directly on a draft invoice streamlines the process of invoicing to help ensure timely and accurate billing. This feature enhances operational efficiency and accelerates cash flow, providing significant financial and administrative benefits to project-oriented companies. This capability is available on lite deployment of Project Operations and with UR 54, is being extended to resource/non-stocked based scenarios deployments as well. 

> [!NOTE]
> The feature is enabled in **Settings** \> **Parameters** \> **Feature control** \> **Enable improvements in invoice creation**.
> Once enabled, the feature can't be disabled.

## Create new invoice line details on a draft proforma invoice

To create new invoice line details on a draft proforma invoice, follow these steps.

1. Select the **New** button on the invoice line form to create an invoice line detail of transaction class time, expense, material, or fee.
1. Update the invoice line detail with price, quantity, billing type, external description, or description.
1. Save the invoice line detail.


## Impact of newly created invoice line details on actuals 

Invoice line details that are manually added to the invoice don't have backing actuals. The backing actuals for these invoice line details are added only on invoice confirmation. 

- **On a Time and material contract line**: Confirming the invoice creates an unbilled sales actual, unbilled sales reversal actual, and billed sales actual for the amount that was specified in the manually added invoice line detail.
- **On a Fixed price Contract line**: Confirming the invoice creates a billed sales actual for the amount that was specified in the manually added invoice line detail.

Learn more about how different invoicing events can impact actuals in [Actuals impact in a time and materials engagement](../actuals/ActualsonTM.md) and [Actuals impact in a fixed price engagement](../actuals/ActualonFP.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
