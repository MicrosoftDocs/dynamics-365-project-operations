---
title: Relaxing project start and end date checks
description: Learn how to relax project start and end date validations during budget creation and during actuals matching in Project Operations.
author: niranjanmaski
ms.date: 10/31/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Relaxing project start and end date checks

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains how to relax project start and end date checks during budget creation and when matching actuals to budgets.

## Why this is needed?

The purpose of budget was to track the actual cost or actual sales against a budgeted cost or sales for the project during the project execution. 
Given this the project cost or sales would happen ideally within the project start date and end date. 
Budgets are designed to track actual costs or sales against planned amounts during project execution. Ideally, these transactions occur within the project start and end dates.  
By default, every budget line and its details are validated against these dates during budget creation.

However, in real-world scenarios, costs or revenues may occur outside the project timeline. Examples include:
- **Preparatory activities** before the official start date.
- **Post-completion expenses** or invoices raised after the project ends.
- Actual transactions that match all budget dimensions except the date.

Without flexibility, such transactions fail to match any budget line, even though they logically belong to the project.

## How these checks can be relaxed?

To address these concern the below 3 parameters are introduced in the project. They are in the **Budget** section of project summary page.

1. **Ignore date constraints when matching budgets to actuals** - Default is No. In case you want the actuals to be matched to budget lines ignoring the date dimensions of budget line compared against the actual transaction date, update this field to Yes.
   In case budget line detail are created after time phasing of budget line. If you update the field to **Yes**, a new line in budget line details is created which is named as **Out of range** which would show the quantity and amount of the actuals which match the budget line with all other dimensions, but it is beyond the budget line start date or end date.
1. **Extend budget start before project start (Years)** - Default is empty. In case you want to create the project budget before the date of the project start date, update the number of years you wanted the check the relaxed.
1. **Extend budget end after project end (Years)** - Default is empty. In case you want to create the project budget after the date of the project end date, update the number of years you wanted the check the relaxed.

> [!NOTE]
> To ensure the budget period and budget line details are created within reasonable time before or project start date, the combined budget extension before the project start date and after the project end date must not exceed two years. For example, you can set as **Extend budget start before project start (Years)** 1 year and **Extend budget end after project end (Years)** as 1 year, making the total extension as 2 years.

> [!NOTE]
> Changes will be applied only in the next revised version of the budget. To reflect the changes in the current budget, delete the existing draft and create a new one.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
