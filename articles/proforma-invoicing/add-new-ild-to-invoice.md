---
title: Adding new invoice line details to a draft invoice
description: This article provides information about how to add new invoice line details to an existing proforma project-based invoice in draft status.
author: suvaidya
ms.date: 02/10/2025
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Add new invoice line details to a draft invoice

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

The ability to create transactions for time, expense, and material usage directly on a draft invoice streamlines the process of invoicing to help ensure timely and accurate billing. This enhances operational efficiency and accelerates cash flow, providing significant financial and administrative benefits to project-oriented companies. This capability is available on lite deployment of Project Operations. With UR 54, this functionality is being extended to integrated deployments as well. 

> [!NOTE]
>The feature can be enabled in Parameters--> settings--> feature control--> **Enable improvements in invoice creation**. Once enabled the feature cannot be disabled.

## How to manually add new invoice line details to a draft proforma invoice
1. Select the **New** button on the invoice form to create an invoice line detail of transaction class time, expense, material or fee.
2. Update the invoice line detail with price, quantity, billing type, external description or description
3. Save the invoice line detail.


## Impact of manually added invoice line details on actuals 
Invoice line details that are manually added to the invoice do not have backing actuals. The backing actuals for these invoice line details are added only on invoice confirmation. 

1. **On a Time and material contract line** : Confirming the invoice, will create an unbilled sales actual , unbilled sales reversal actual and billed sales actual for the amount that was specified in the manually added invoice line detail.
2. **On a FP Contract line** : Confirming the invoice will create a billed sales actual for the amount that was specified in the manually added invoice line detail.

To learn more about the impact of different billing events on actuals refer [Actuals impact in a time and materials engagement](ActualsonTM.md) and [Actuals impact in a fixed price engagement](ActualonFP.md)
