---
title: Project Revenue recognition using the cost estimate instead of the estimate cost at completion
description: Learn how to configure and generate revenue recognition using cost estimates instead of EAC (Estimate cost at completion).
author: mukumarm
ms.date: 03/10/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Set up cost templates

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for Manufacturing_ 

Actual costs often exceed initial estimates due to scope changes, resource constraints, or unforeseen expenses. 
If EAC is updated dynamically, revenue recognition can become inconsistent, leading to premature recognition or inflated revenue figures. 
Finance teams always require a stable and auditable method that uses the original cost estimate as the denominator for percentage completion calculations. 
This ensures that revenue recognition remains aligned with the initial plan, and any cost overruns are treated as losses rather than revenue triggers.

This feature provides predictable revenue recognition, simplifies compliance with IFRS/GAAP, and enhances auditability. 
By decoupling revenue recognition from dynamic EAC adjustments, It ensures financial stability and transparency. 
Overruns are clearly identified as losses, enabling better cost control and project governance.

This article explains how to configure and generate **revenue recognition using cost estimates** instead of **EAC (Estimate cost at completion)** in **Dynamics 365 Project operations** for **fixed price projects**
or fixed price contract lines.

## Prerequisites
### Minimum version required
To use the feature for **Dynamics 365 Project Operations**, you must have the following versions:
-  Dynamics 365 Finance version 10.0.48 or later
### Features
To use the functionality, activate the following features:
-  Enable Project Revenue recognition using the cost estimate instead of the EAC in Project Operations

## Configurations

### Cost templates
To enable the fixed price revenue recognition percentage calculation using cost estimates (forecast or project budget), follow these steps: 

1. In **Dynamics 365 Finance**, Go to **Project management and accounting** > **Setup** > **Estimates** > **Cost templates**.
2. Click **Cost lines**.
3. Select Cost line and in the General tab, Select **Cost to complete method** as **Total forecast - actual**.
4. Enable **Use forecast amount for revenue recognition** to **Yes**. Select this option to use the forecast amount,
   rather than actual project cost, for revenue recognition calculations.

 > [!NOTE]
   > This feature is supported only for the **Completion method** based on **Cost amount** and **Quantity**.

### Project management and accounting parameters

If the cost to complete is lower than the estimated cost at completion, **Dynamics 365** blocks revenue recognition for the period.
To allow processing while notifying the user, the system should display a warning and permit continuation as outlined below.

1. In **Dynamics 365 Finance**, Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
2. Go to **Revenue recognition** tab.
3. Set **Allow posting when cost to complete is less than the check value** to **Warning**.

## Example
Once this option is enabled, during the **revenue recognition process**, **Dynamics 365** evaluates the **cost template** and **cost-to-complete** method as follows:
If **Actual cost > Forecast amount** then consider Total cost = Total forecast amount for percentage of completion calculation.

### Forecast

| Estimates type | Dollar cost or units | 
| --- | --- |
| Hour | 1,900.00 |
| Expense | 2,000.00 |
| Item | 1,500.00 |
| **Total** | 5,400.00 |

### Transactions

| Transactions Period | Hour | Expense| Item | Total cost for the month | Total cost | Current Percentage of completion | Current percentange of completion Calculation | Percentage of completion| New Percentage of completion Calculation |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | ---|
| November | 1,000.00 | 400.00 || 1,400 |1,400|25.93%|(1,400/5,400)*100|25.93%|(1,400/5,400)*100|
| December | 1,400.00 | 1,000.00 || 2,400 |3,800|**64.41%**|(1,400/5,800)*100|**70.37%**|(3,800/5,400)*100|                                                       -   	 	 	 	 

