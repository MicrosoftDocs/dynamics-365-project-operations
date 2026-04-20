---
title: Use time-phased project cost budget lines
description: This article explains how to time-phase project budget lines and create budget line details.
author: niranjanmaski
ms.date: 02/26/2026
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

You create budget lines with specified start and end dates. You allocate a specific quantity or amount across selected dimensions for budgeting. Time phasing distributes this budgeted quantity and amount over the time span between the start and end dates of the budget line. This distribution considers work hours according to the work hour calendars and ensures proportional allocation for time budget lines.

## Prerequisite for time phasing of budget lines

You must create a budget period at the project level. Time phasing of project cost budget lines requires a budget period to accurately determine work hours. For information about how to set up a budget period at the project level, see [Set up a budget period](budget-period-setup.md).

> [!NOTE]
> Set up the budget period before you create a budget line. This way, you ensure that time phasing of the budget line into its details happens during the budget line creation process.

## Automatic time phasing during budget line creation

After you set up the budget period at the project level, the process of time-phasing budget lines and creating budget line details happens automatically. This process applies to both cases: when you [manually create](create-delete-project-budget.md) a budget line and when you [generate a budget line from estimates](create-project-budget-from-estimates.md).

## On-demand time phasing of budget lines

You can do on-demand time phasing of a budget line, provided that the budget version remains in **Draft** status.

To time-phase a budget line, follow these steps:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the project you want to open the project main page.
1. On the **Budget** tab, make sure that the budget and budget line exist, and that the budget version status is **Draft**.
1. Select the project budget line that you want to time-phase.
1. Select **Time Phase**.
1. After the budget line is time-phased, you see the creation of budget line details.
1. Select the right arrow (**\>**) on the left of the budget line to view the nested grid that includes budget line details.

## What happens when you time-phase budget lines?

For Time, Material, and Expense budget lines, time phasing works differently depending on the transaction class.

### Time budget lines

The behavior of time phasing for time budget lines varies, depending on whether the **Resource** field is set on the budget line. It also depends on the **Amount Method** value at the budget line level.

If you set the **Resource** field, the following behavior occurs:

1. The resource's calendar calculates working hours between the start and end dates of the budget line.
1. If you set the **Amount Method** field of the budget line to **Quantity \* Unit price**, and you define the number of hours on the budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. The system calculates the amount in the budget line details as *Quantity* &times; *Unit price*.
1. If you set the **Amount Method** field to **Fixed Price**, and you don't define the number of hours, the budgeted amount is distributed in proportion to the working hours according to the budget period.
1. Rounding is done to two decimal places by default.
1. The system adjusts any remaining quantity or amount after distribution across the budget period with the last budget line detail's amount or quantity, so that the total matches the budget.

If you don't set the **Resource** field, the following behavior occurs:

1. The project's calendar calculates working days between the start and end dates of the budget line.
1. Working hours are calculated as eight hours per day for all working days at the project level by default.
1. If you set the **Amount Method** field of the budget line to **Quantity \* Unit price**, and you define the number of hours on the budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. The system calculates the amount in the budget line details as *Quantity* &times; *Unit price*.
1. If you set the **Amount Method** field to **Fixed Price**, and you don't define the number of hours, the budgeted amount is distributed in proportion to the working hours according to the budget period.
1. Rounding is done to two decimal places by default.
1. The system adjusts any remaining quantity or amount after distribution across the budget period with the last budget line detail's amount or quantity, so that the total matches the budget.

### Expense budget lines

The behavior of time phasing for expense budget lines depends on the **Amount Method** value at the budget line level.

1. If you set the **Amount Method** field of the budget line to **Quantity \* Unit price** and define the quantity of the expense on the budget line, the system evenly distributes the expense quantity across the budget period between the start and end dates of the budget line.
1. The system calculates the amount in the budget line details as *Quantity* &times; *Unit price*.
1. If you set the **Amount Method** field to **Fixed Price** and don't define the quantity of the expense, the system evenly distributes the budgeted expense amount across the budget period between the start and end dates of the budget line.
1. Rounding is done to two decimal places by default.
1. The system adjusts any remaining quantity or amount after distribution across the budget period with the last budget line detail's amount or quantity, so that the total matches the budget.

### Material budget lines

The behavior of time phasing for material budget lines depends on the **Amount method** value at the budget line level.

1. If you set the **Amount Method** field of the budget line to **Quantity \* Unit price** and define the quantity of material on the budget line, the system evenly distributes that quantity across the budget period between the start and end dates.
1. The system calculates the amount in the budget line details as *Quantity* &times; *Unit price*.
1. If you set the **Amount Method** field to **Fixed Price** and don't define the quantity of material, the system evenly distributes the budgeted amount across the budget period between the start and end dates.
1. For write-in products, the system rounds to two decimal places by default.
1. For existing products, the system applies the rounding setting on the product.
1. The system adjusts any remaining quantity or amount after distribution across the budget period with the last budget line detail's amount or quantity, so that the total matches the budget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
