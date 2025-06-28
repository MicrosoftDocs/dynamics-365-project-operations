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

_**Applies To:** Core deployment - deal to proforma invoicing, Project Operations Integrated with ERP_

On a new invoice, the invoice line details can be updated when the **Project Invoice Status** field on the invoice header is set to **Draft**. On a revised (corrected) invoice, the invoice line details can be updated if they are associated with an invoice line that has the **Time and Material** billing method.

To update an invoice line detail on an existing draft invoice, follow these steps.

1. Select the invoice line.
1. Select **Edit**.
1. Select the invoice line detail to edit.
1. Select **Edit**.

## Editable fields on invoice line details for an invoice line that has the Time and Material billing method

The following out-of-box fields can be updated on an invoice line detail in **Draft** status:

- Billing type
- Quantity
- Price
- Tax
- Description
- External Description

## Editable fields on an invoice line detail for an invoice line that has the Fixed Price billing method

The following fields can be edited on an invoice line detail for an invoice line that has the **Fixed Price** billing method:

- Billing Type
- Tax
- Description
- External Description

> [!NOTE]
> The **Transaction Classification** field should not be updated on an invoice line detail. Otherwise, a mismatch occurs between the transaction classification on the unbilled sales actual and transaction classification on the billed sales actual.
>
> In Update Release (UR) 55, a back-end validation was added to prevent this scenario. This validation is automatically enabled. It applies to all invoice line details, regardless of whether they were created from backing actuals or manually created directly on the invoice. If the **Transaction Classification** field has to be updated on a manually created invoice line detail, you must delete the invoice line detail and create a new one.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
