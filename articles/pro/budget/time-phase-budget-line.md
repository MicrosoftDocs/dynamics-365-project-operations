---
title: Time phase project cost budget lines 
description: This article explains how to time phase the project budget lines and create budget line details. 
author: niranjanmaski
ms.date: 25/07/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

#  Time phase project cost budget lines

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

## What is time phasing of project budget lines

Budget lines are created within a specified start and end date, allocating a specific quantity or amount across chosen dimensions for budgeting. Time phasing then  distributes this budgeted quantity and amount over the time span between the start and end dates of the budget line. 

This distribution considers work hours according to the work hour calendars, ensuring proportional allocation for time budget lines.

## Prerequisite to time phase a budget line

As a prerequisite, the time phasing of project cost budget lines requires the creation of a budget period at the project level. 

This is necessary to determine work hours accurately. Please refer to [Budget period setup ](budget-period-setup.md) for instructions on setting up the budget period at the project level before proceeding with time phasing.

> [!NOTE]
> As a best practice, it's recommended to set up the budget period before creating a budget line. This ensures that the time phasing of the budget line into its details is completed during the budget line creation process itself. 

## Automatic time phasing during budget line creation

Once the budget period is configured at the project level, the process of time phasing budget lines and creating budget line details will occur automatically. This applies to both cases: when a budget line is [created manually](create-delete-project-budget.md) or when it's [generated from estimates](create-project-budget-from-estimates.md).

## On demand time phasing of budget line

You can perform on-demand time phasing of the budget line as long as the budget version remains in **Draft** status. 

Here are the steps to time phase a budget line.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on **Projects** in the left-hand navigation to view the list of active projects.
1. Find and click on the desired project to open its main form.
1. Open the **Budget** tab on the project main form.
1. Ensure that the budget and budget line are created, and the budget version status is in **Draft** status.
1. Select the project budget line you intend to time phase.
1. Click the **Time Phase** button located at the top of the budget grid.
1. Once time phased, observe the creation of budget line details.
1. Click the chevron on the left of the budget line to view the nested grid with budget line details.

## What happens when a budget line is time phased

Time phasing of Time, Material and Expense budget lines will be as per the below explanation of each transaction class.

### Time budget line

The behavior of time phasing for Time budget lines varies depending on whether the **Resource** field is filled in the budget line or not along with the **Amount method** at budget line level.

If the **Resource** field is filled. 

1. The resource's calendar is used to calculate working hours between the start and end date of the budget line.
1. If the **Amount Method** of the budget line is **Quantity * Price**, where the quantity of hours is defined in budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. Amount in budget line details is calculated as **quantity * unit price.**
1. If the **Amount Method** is **Fixed Price**, where the quantity of hours isn't defined, the budgeted amount is distributed in proportion to the working hours as per the budget period.
1. Rounding is defaulted to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity so that the total matches the budget.

If the **Resource** field is not filled.

1. The project's calendar is used to calculate working days between the start and end date of the budget line.
1. Working hours are calculated as default 8 hrs per day for all working days at project level.
1. If the **Amount Method** of the budget line is **Quantity * Price**, where the quantity of hours is defined in budget line, the budgeted hours are distributed in proportion to the working hours according to the budget period.
1. Amount in budget line details is calculated as **quantity * unit price.**
1. If the **Amount Method** is **Fixed Price**, where the quantity of hours isn't defined, the budgeted amount is distributed in proportion to the working hours as per the budget period.
1. Rounding is defaulted to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity so that the total matches the budget.

### Expense budget line
The behavior of time phasing for Expense budget lines is determined by **Amount method** at the budget line level. 

1. If the **Amount Method** of the budget line is **Quantity * Price**, where the quantity of expense is defined in budget line, expense quantity is distributed **equally** across the budget period between start and end date of the budget line. 
1. The amount in budget line details is calculated as **quantity * unit price.**
1. If the **Amount Method** is **Fixed Price**, where the quantity of expense isn't defined, the budgeted expense amount is distributed **equally** across the budget period between start and end date of the budget line. 
1. Rounding is defaulted to two decimal places.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity so that the total matches the budget.

### Material budget line
The behavior of time phasing for Material budget lines is determined by **Amount method** at the budget line level. 

1. If the **Amount Method** is **Quantity * Price**, and the budget line specifies a quantity of material, that quantity is evenly distributed across the budget period between the start and end dates.
1. The amount in budget line details is calculated as **quantity * unit price.**
1. If the **Amount Method** is **Fixed Price**, and no quantity of material is defined, the budgeted amount is equally distributed across the budget period between the start and end dates.
1. For write-in products, rounding is defaulted to two decimal places.
1. For existing products, the rounding setting on the product is applied.
1. Any remaining quantity or amount after distribution across the budget period is adjusted with the last budget line detail's amount or quantity so that the total matches the budget.
	
	
[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
