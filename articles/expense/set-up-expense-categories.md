---
title: Set up expense categories
description: This article provides information about how to set up expense categories and shared categories for expense reports.
author: mukumarm 
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
 
---

# Set up expense categories

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

When employees create expense reports, each expense that they record must be associated with an expense category. Expense categories are derived from shared categories that can be shared across the legal entities in your organization. Depending on how your organization is defined, these expense categories can also be shared in other areas. Based on the definition of your organization and guidance from the implementation team, you must determine whether the categories that are used in Expense management will be used only in Expense management or should be shared in other areas.

> [!NOTE]
> These categories can be shared between Project management and accounting and Expense management, or between Project management and accounting and Production. However, they can't be shared between Expense management and Production.

Before you can begin the setup process, the following decisions must be made for each expense category:

- What is the expense category? Examples include categories for flights, hotel, or mileage.
- Can the expense category also be used in Project management and accounting? If it can, you must also make the following decisions:

    - Which cost accounts will be used for the following expenses?

        - Cost
        - Payroll allocation
        - WIP-cost value
        - Cost-item
        - WIP-cost value-item
        - Accrued loss
        - WIP-accrued loss

    - Which revenue accounts will be used for the following sources of revenue?

        - Invoiced revenue
        - Accrued revenue-sales value
        - WIP-sales value
        - Accrued revenue-production
        - WIP-production
        - Accrued revenue-profit
        - WIP-profit
        - Accrued revenue-subscription
        - WIP-subscription

- What is the expense type?
- What is the default payment method for the expense category?
- Do expenses in the expense category have to be itemized?
- What is the main default account for the expense category?
- What is the default item sales tax group for the expense category?
- Are additional payment methods allowed for the expense category? If so, what are they?
- Are there subcategories in this expense category? If there are subcategories, you must also make the following decisions:

    - Are any of the subcategories excluded from tax recovery?
    - What is the item sales tax group of the subcategories?


[!INCLUDE[footer-include](../includes/footer-banner.md)]
