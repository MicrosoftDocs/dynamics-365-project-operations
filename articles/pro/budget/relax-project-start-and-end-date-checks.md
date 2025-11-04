---
title: Relax project start and end date checks
description: Learn how to relax the project start and end date validations during budget creation and during actuals matching in Dynamics 365 Project Operations.
author: niranjanmaski
ms.date: 11/04/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Relax project start and end date checks

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP and Project Operations Core._

This article explains how to relax project start and end date checks during budget creation and when matching actuals to budgets.

## Why is this relaxation configuration needed?

The purpose of a budget is to track the actual cost or actual sales against a budgeted cost or sales for the project during the project execution.

The project cost or sales ideally happens within the project start date and end date. Budgets are designed to track actual costs or sales against planned amounts during project execution. Ideally, these transactions occur within the project start and end dates.  
By default, every budget line and its details are validated against these dates during budget creation.

However, in real-world scenarios, costs or revenues might occur outside the project timeline. Examples include:

- Preparatory activities before the official start date.
- Post-completion expenses or invoices raised after the project ends.
- Actual transactions that match all budget dimensions except the date.

Without flexibility, you can't create a budget line before or after the project start and end date.
Actuals related to such transactions also fail to match any budget line, even though they logically belong to the project.

## How can you relax these checks?

To address this issue, the **Budget** section of the project summary page provides three parameters:

1. **Ignore date constraints when matching budgets to actuals**  
   - **Default:** No  
   - Set to **Yes** to match actuals to budget lines regardless of date.  
   - When enabled, any out-of-range actuals appear in a new budget line detail named **Out of range**, showing quantity and amount for transactions outside the budget line dates.

1. **Extend budget start before project start (Years)**  
   - **Default:** Empty  
   - Specify the number of years to allow budget creation before the project start date.

1. **Extend budget end after project end (Years)**  
   - **Default:** Empty  
   - Specify the number of years to allow budget creation after the project end date.

> [!NOTE]
> To ensure the budget period and budget line details are created within reasonable time before or after the project start date, the combined extension before and after the project dates must not exceed **two years**. For example, you can set **1 year before** and **1 year after**, totaling 2 years.

> [!NOTE]
> Changes apply only in the next draft version of the budget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
