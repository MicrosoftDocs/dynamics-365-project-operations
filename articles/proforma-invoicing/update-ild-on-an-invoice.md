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

The invoice line details on a new invoice can be updated when the **Project Invoice Status** on the Invoice header has a **Draft** status.
On a revised (corrected) invoice , the invoice line detail(s) can be updated if it is associated to an invoice line having **Time and Material** billing method.

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

[!INCLUDE[banner](../includes/banner.md)]

To update an invoice line detail on an existing draft invoice -
1. Select the invoice line 
2. Select Edit
3. Select invoice line detail to edit
4. Select edit

## Editable fields on an invoice line detail for an Invoice line with Time and Material Billing method
The following OOB fields are allowed to be updated on an Invoice line detail in draft status:
1. Billing type
2. Quantity
3. Price
4. Tax
5. Description
6. External Description

## Editable fields on an invoice line detail for an Invoice line with Fixed Price Billing method
1. Billing Type
2. Tax
3. Description
4. External Description

> [!NOTE]
> **Transaction Classification** should not be updated on an Invoice line detail. This is because doing so, results in a mimatch between the transaction classification on the unbilled sales actual and the billed sales actual. 
In UR 55, a backend validation has beeen added to prevent this scenario and will be automatically enabled.
The validation applies to all invoice line details, irrespective of whether these were created from backing actuals or manually created directly on the invoice. If there is a need to update the Transaction classification on a manually created invoice line detail, user must delete the Invoice line detail and create a new one. 

