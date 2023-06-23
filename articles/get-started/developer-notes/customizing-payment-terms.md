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

When adding customized Payment Terms options to the account entity, developers must also add it to the option set in Quote customer and Project contract customer entity. Not doing so, can result in the following error - 

**Exception Message:** A validation error occurred. The value {0} of 'msdyn_paymentterms' on record of type 'msdyn_projectcontractsplitbillingrule' is outside the valid range. Accepted Values: {1}
**Example:** Exception Message: A validation error occurred. The value 5 of 'msdyn_paymentterms' on record of type 'msdyn_projectcontractsplitbillingrule' is outside the valid range. Accepted Values: 1,2,3,192350001


## Steps for customizing payment terms optionset

In the Project Contract Customer entity, navigate to **Customizations -> Entities -> Project contract Customer -> Fields -> Payment terms (msdyn_paymentterms) -> Add option**
In the Quote customer entity, go to **Customizations -> Entities -> Quote Customer -> Fields -> Payment terms (msdyn_paymentterms) -> Add option**
Publish all customizations
