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
- Preparatory activities before the official start date.
- Post-completion expenses or invoices raised after the project ends.
- Actual transactions that match all budget dimensions except the date.

Without flexibility, such transactions fail to match any budget line, even though they logically belong to the project.

## How these checks can be relaxed?

To address this, three parameters are available in the **Budget** section of the project summary page:

1. **Ignore date constraints when matching budgets to actuals**  
   - **Default:** No  
   - Set to **Yes** to match actuals to budget lines regardless of date.  
   - When enabled, any out-of-range actuals appear in a new budget line detail named **Out of range**, showing quantity and amount for transactions outside the budget line dates.

2. **Extend budget start before project start (Years)**  
   - **Default:** Empty  
   - Specify the number of years to allow budget creation before the project start date.

3. **Extend budget end after project end (Years)**  
   - **Default:** Empty  
   - Specify the number of years to allow budget creation after the project end date.


> [!NOTE]
> To ensure the budget period and budget line details are created within reasonable time before or project start date, the combined extension before and after the project dates must not exceed **two years**. For example, you can set **1 year before** and **1 year after**, totaling 2 years.


> [!NOTE]
> Changes will be applied only in the next draft version of the budget. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
