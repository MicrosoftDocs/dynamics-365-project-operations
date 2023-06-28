---
title: Developer notes for Payment Terms
description: This article provides additional developer information about working with payment terms.
author: suvaidya
ms.date: 06/23/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Developer notes for Payment terms 

When adding customized payment terms options to the account entity, developers must also add it to the option set in the **Quote customer** and **Project contract customer** entities. 
Not adding the customized payment terms options, can result in the following error message displaying in all scenarios that involve the creation of a quote customer or a project contract customer. 

**Example of the Exception Message:** 

``` console
A validation error occurred. The value 5 of 'msdyn_paymentterms' on record of type 'msdyn_projectcontractsplitbillingrule' is outside the valid range. Accepted Values: 1,2,3,192350001.
```

In addition to the error message, impact is also seen in the scenarios listed below when the Quote customers and Project contract customers are created via lazy upgrade. 

- Confirmation of a contract.
- Submission of a time, expense, or material usage log.
- Creation of milestone.
- Invoicing from contract or via schedule, creation of invoice lines, and creation of invoice for products. 
- Update of a Customer on project contract or quote. 
- Creation of actuals during approval or journal correction.
- Creation of invoice line detail.

### Customize the payment terms options

To customize the payment terms options, follow these steps.

1. In the Project Contract Customer entity, navigate to **Customizations** > **Entities** > **Project contract Customer** > **Fields** > **Payment terms (msdyn_paymentterms)** > **Add option**.

:::image type="content" source="media/adding-payment-terms.png" alt-text="Screenshot of Payment terms of Project contract customer."::: 

2. In the Quote customer entity, navigate to **Customizations** > **Entities** > **Quote Customer** > **Fields** > **Payment terms (msdyn_paymentterms)** > **Add option**.
3. Publish all customizations.
