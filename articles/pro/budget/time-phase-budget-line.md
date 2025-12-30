---
title: Use time-phased project cost budget lines
description: This article explains how to time-phase project budget lines and create budget line details.
author: nimaski
ms.date: 06/24/2024
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: nimaski
ms.custom: 
  - bap-template
---

# Use time-phased project cost budget lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains how to time-phase project budget lines and create budget line details.

## What is time phasing of project budget lines?

Budget lines are created within specified start and end dates, and allocate a specific quantity or amount across selected dimensions for budgeting. Time phasing distributes this budgeted quantity and amount over the time span between the start and end dates of the budget line. This distribution considers work hours according to the work hour calendars and ensures proportional allocation for time budget lines.

## Prerequisite for time phasing of budget lines

As a prerequisite, you must create a budget period at the project level. Time phasing of project cost budget lines requires a budget period to accurately determine work hours. For information about how to set up a budget period at the project level, see [Set up a budget period](budget-period-setup.md).

> [!NOTE]
> We recommend that you set up the budget period before you create a budget line. In this way, you ensure that time phasing of the budget line into its details is done during the budget line creation process.

## Automatic time phasing during budget line creation

After the budget period is set up at the project level, the process of time-phasing budget lines and creating budget line details occurs automatically and applies to both cases: when a budget line is [manually created](create-delete-project-budget.md) and when it's [generated from estimates](create-project-budget-from-estimates.md).

## On-demand time phasing of budget lines

You can do on-demand time phasing of a budget line, provided that the budget version remains in **Draft** status.

To time-phase a budget line, follow these steps:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the **Budget** tab, ensure that the budget and budget line are created, and that the budget version status is in **Draft** status.
1. Select the project budget line that you want to time-phase.
1. Select **Time Phase**.
1. After the budget line is time-phased, observe the creation of budget line details.
1. Select the right arrow (**\>**) on the left of the budget line to view the nested grid that includes budget line details.

## What happens when budget lines are time-phased?

For Time, Material, and Expense budget lines, time phasing behaves differently, depending on the transaction class.

### Time budget lines

The behavior of time phasing for Time budget lines varies, depending on whether the **Resource** field is set on the budget line. It also depends on the **Amount Method** value at the budget line level.

If the **Resource** field is set, the following behavior occurs:

1. The resource's calendar is used to calculate working hours between the start and end dates of the budget line.
1. If the **Amount Method** field of the budget line is set to **Quantity \* Unit price**, and the number of hours is defined on the budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. The amount in the budget line details is calculated as *Quantity* &times; *Unit price*.
1. If the **Amount Method** field is set to **Fixed Price**, and the number of hours isn't defined, the budgeted amount is distributed in proportion to the working hours according to the budget period.
1. By default, rounding is done to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity, so that the total matches the budget.

If the **Resource** field isn't set, the following behavior occurs:

1. The project's calendar is used to calculate working days between the start and end dates of the budget line.
1. By default, working hours are calculated as eight hours per day for all working days at the project level.
1. If the **Amount Method** field of the budget line is set to **Quantity \* Unit price**, and the number of hours is defined on the budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. The amount in the budget line details is calculated as *Quantity* &times; *Unit price*.
1. If the **Amount Method** field is set to **Fixed Price**, and the number of hours isn't defined, the budgeted amount is distributed in proportion to the working hours according to the budget period.
1. By default, rounding is done to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity, so that the total matches the budget.

### Expense budget lines

The behavior of time phasing for Expense budget lines depends on the **Amount Method** value at the budget line level.

1. If the **Amount Method** field of the budget line is set to **Quantity \* Unit price**, and the quantity of the expense is defined on the budget line, the expense quantity is evenly distributed across the budget period between the start and end dates of the budget line.
1. The amount in the budget line details is calculated as *Quantity* &times; *Unit price*.
1. If the **Amount Method** field is set to **Fixed Price**, and the quantity of the expense isn't defined, the budgeted expense amount is evenly distributed across the budget period between the start and end dates of the budget line.
1. By default, rounding is done to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity, so that the total matches the budget.

### Material budget lines

The behavior of time phasing for Material budget lines depends on the **Amount method** value at the budget line level.

1. If the **Amount Method** field of the budget line is set to **Quantity \* Unit price**, and the quantity of material is defined on the budget line, that quantity is evenly distributed across the budget period between the start and end dates.
1. The amount in the budget line details is calculated as *Quantity* &times; *Unit price*.
1. If the **Amount Method** field is set to **Fixed Price**, and the quantity of material isn't defined, the budgeted amount is evenly distributed across the budget period between the start and end dates.
1. For write-in products, rounding is done to two decimal places by default.
1. For existing products, the rounding setting on the product is applied.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity, so that the total matches the budget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
