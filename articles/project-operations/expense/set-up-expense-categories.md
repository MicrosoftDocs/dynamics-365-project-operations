---
# required metadata

title: Set up expense categories
description: This topic provides information about how to set up expense and shared categories for expense reports.
author: suvaidya
manager: AnnBe
ms.date: 07/23/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

ms.search.form: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: 
# ms.search.industry: 
ms.author: shylaw
ms.search.validFrom: 
ms.dyn365.ops.version: 
---

# Set up expense categories

When employees create an expense report, each expense that they record must be associated with an expense category. Expense categories are derived from shared categories that can be shared across the legal entities in your organization. These categories can also be shared in other areas, depending on the way that your organization is defined. Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared in other areas. Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production. You must make the following decisions for each expense category.

Decisions:

- What is the expense category? Examples include categories for flights, hotel, or mileage.
- Can the expense category also be used in Project management and accounting?
- What is the expense type?
- What is the default payment method for the expense category?
- Do expenses in the expense category have to be itemized?
- What is the main default account for the expense category?
- What is the default item sales tax group for the expense category?
- Are additional payment methods allowed for the expense category? If additional payment methods are allowed, what are they?
- Are there subcategories in this expense category? If there are subcategories, you must also make the following decisions:

    - Are any of the subcategories excluded from tax recovery?
    - What is the item sales tax group of the subcategories?

If the expense category is also used in Project management and accounting, answer the remaining questions. 

- Which cost accounts will be used for the following expenses?

    - Cost
    - Payroll allocation
    - WIP-cost value
    - Cost-item
    - WIP-cost value-item
    - Accrued loss
    - WIP-accrued loss

- Which revenue accounts will be used for the following?

    - Invoiced revenue
    - Accrued revenue-sales value
    - WIP-sales value
    - Accrued revenue-production
    - WIP-production
    - Accrued revenue-profit
    - WIP-profit
    - Accrued revenue-subscription
    - WIP-subscription
