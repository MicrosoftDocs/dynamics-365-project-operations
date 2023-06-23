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

When adding customized Payment Terms options to the account entity, developers must also add it to the option set in Quote customer and Project contract customer entity. 
Not doing so, can result in the below error in all scenarios that involve creation of a quote customer or a project contract customer . 

**Example of the Exception Message:** A validation error occurred. The value 5 of 'msdyn_paymentterms' on record of type 'msdyn_projectcontractsplitbillingrule' is outside the valid range. Accepted Values: 1,2,3,192350001

Impact is also seen in the below scenarios when Quote customers and contract customers are created via lazy upgrade - 

1. Confirmation of a contract
2. Submission of time/expense/material usage log
3. Creation of milestone 
4. Invoicing  from contract or via schedule , Creation of invoice lines  and Creation of invoice for products 
5. Update of Customer on project contract  or quote 
6. Creation of actuals during approval or journal correction .
7. Creation of invoice line detail .

### Steps for customizing payment terms optionset

In the Project Contract Customer entity, navigate to **Customizations -> Entities -> Project contract Customer -> Fields -> Payment terms (msdyn_paymentterms) -> Add option**

![Payment terms of Project contract customer.](media/Adding_PaymentTerms.png)

In the Quote customer entity, go to **Customizations -> Entities -> Quote Customer -> Fields -> Payment terms (msdyn_paymentterms) -> Add option**
Publish all customizations
