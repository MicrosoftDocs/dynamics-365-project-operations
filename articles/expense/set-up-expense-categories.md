---
title: Set up expense categories
description: Learn how to set up expense categories and shared categories for expense reports in your organization. Follow these steps to streamline expense management.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
 
---

# Set up expense categories

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

When employees create expense reports, they must associate each expense with an expense category. Expense categories come from shared categories that you can share across the legal entities in your organization. Depending on how your organization is defined, you can share these expense categories in other areas. Based on the definition of your organization and guidance from the implementation team, determine whether the categories that you use in Expense management are used only in Expense management or shared in other areas.

> [!NOTE]
> You can share these categories between Project management and accounting and Expense management, or between Project management and accounting and Production. However, you can't share them between Expense management and Production.

Before you begin the setup process, make the following decisions for each expense category:

- What is the expense category? Examples include categories for flights, hotel, or mileage.
- Can the expense category also be used in Project management and accounting? If it can, make the following decisions:

  - Which cost accounts do you use for the following expenses?

    - Cost
    - Payroll allocation
    - WIP-cost value
    - Cost-item
    - WIP-cost value-item
    - Accrued loss
    - WIP-accrued loss

  - Which revenue accounts do you use for the following sources of revenue?

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
- Are there subcategories in this expense category? If there are subcategories, make the following decisions:

  - Are any of the subcategories excluded from tax recovery?
  - What is the item sales tax group of the subcategories?

[!INCLUDE[footer-include](../includes/footer-banner.md)]
