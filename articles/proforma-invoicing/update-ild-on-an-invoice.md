---
title: Update invoice line details on a draft project-based proforma invoice
description: Learn how to update invoice line details on an existing proforma project-based invoice that is in Draft status.
author: suvaidya
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Update invoice line details on a draft project-based proforma invoice

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

On a new invoice, you can update the invoice line details when you set the **Project Invoice Status** field on the invoice header to **Draft**. On a revised (corrected) invoice, you can update the invoice line details if they're associated with an invoice line that uses the **Time and Material** billing method.

To update an invoice line detail on an existing draft invoice, follow these steps:

1. Select the invoice line.
1. Select **Edit**.
1. Select the invoice line detail to edit.
1. Select **Edit**.

## Editable fields on invoice line details for an invoice line that uses the Time and Material billing method

You can update the following out-of-box fields on an invoice line detail in **Draft** status:

- Billing type
- Quantity
- Price
- Tax
- Description
- External Description

## Editable fields on an invoice line detail for an invoice line that uses the Fixed Price billing method

You can edit the following fields on an invoice line detail for an invoice line that uses the **Fixed Price** billing method:

- Billing Type
- Tax
- Description
- External Description

> [!NOTE]
> Don't update the **Transaction Classification** field on an invoice line detail. If you update this field, the transaction classification on the unbilled sales actual doesn't match the transaction classification on the billed sales actual.
>
> In Update Release (UR) 55, the product team added back-end validation to prevent this mismatch. The validation is automatically enabled. It applies to all invoice line details, regardless of whether you created them from backing actuals or you manually created them directly on the invoice. If you need to update the **Transaction Classification** field on a manually created invoice line detail, you must delete the invoice line detail and create a new one.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
