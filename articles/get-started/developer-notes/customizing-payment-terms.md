---
title: Developer notes for payment terms
description: This article provides more developer information about working with payment terms.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Developer notes for payment terms

[!INCLUDE[banner](../../includes/banner.md)]

_Applies To: Project Operations Integrated with ERP, Project Operations Core_

If a developer adds customized payment term options to the account entity, they must also add them to the option set in the **Quote customer** and **Project contract customer** entities. Otherwise, the following error message can be shown in all scenarios that involve the creation of a quote customer or a project contract customer:

> A validation error occurred. The value 5 of 'msdyn\_paymentterms' on record of type 'msdyn\_projectcontractsplitbillingrule' is outside the valid range. Accepted Values: 1,2,3,192350001.

In addition to the error message, impact is experienced in the following scenarios when quote customers and project contract customers are created via lazy upgrade:

- Confirmation of a contract
- Submission of a time, expense, or material usage log
- Creation of a milestone
- Invoicing from a contract or via a schedule, creation of invoice lines, and creation of an invoice for products
- Update of a customer on a project contract or quote
- Creation of actuals during approval or journal correction
- Creation of invoice line details

## Customize the payment terms options

To customize the payment terms options, follow these steps:

1. In the **Project contract customer** entity, go to **Customizations** \> **Entities** \> **Project contract Customer** \> **Fields** \> **Payment terms (msdyn\_paymentterms)**, and select the **Add option** button (**\+**).

    :::image type="content" source="media/adding-payment-terms.png" alt-text="Screenshot that shows the Add option button on the Payment terms of Project Contract Customer page.":::

1. In the **Quote customer** entity, go to **Customizations** \> **Entities** \> **Quote Customer** \> **Fields** \> **Payment terms (msdyn\_paymentterms)**, and select the **Add option** button (**\+**).
1. Publish all customizations.
