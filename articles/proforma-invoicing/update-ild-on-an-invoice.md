---
title: Update invoice line details on a draft project-based proforma invoice
description: Learn how to update invoice line details on an existing proforma project-based invoice that is in Draft status.
author: suvaidya
ms.date: 03/21/2025
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Update invoice line details on a draft project-based proforma invoice

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

The invoice line details on a new invoice can be updated when the **Project Invoice Status** on the Invoice header has a **Draft** status.
On a revised (corrected) invoice, the invoice line details can be updated if it is associated to an invoice line that has the **Time and Material** billing method.

To update an invoice line detail on an existing draft invoice, follow these steps.

1. Select the invoice line. 
2. Select **Edit**.
3. Select invoice line detail to edit.
4. Select **Edit**.

## Editable fields on an invoice line detail for an invoice line with the time and material billing method

The following out-of-the-box fields can be updated on an invoice line detail in draft status:

- Billing type
- Quantity
- Price
- Tax
- Description
- External Description

## Editable fields on an invoice line detail for an invoice line with the fixed price billing method

The following fields can be edited on an invoice line detail for and invoice line with the fixed price billing method:

- Billing Type
- Tax
- Description
- External Description

> [!NOTE]
> **Transaction Classification** should not be updated on an invoice line detail. Doing so results in a mimatch between the transaction classification on the unbilled sales actual and the billed sales actual. 
>
>In UR 55, a backend validation was added to prevent this scenario and is automatically enabled.
The validation applies to all invoice line details, irrespective of whether these were created from backing actuals or manually created directly on the invoice. If there is a need to update the Transaction classification on a manually created invoice line detail, you must delete the invoice line detail and create a new one. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
