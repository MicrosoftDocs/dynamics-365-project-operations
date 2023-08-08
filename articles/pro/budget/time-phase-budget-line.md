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

## On demand phasing of budget line

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



To enable project cost budgeting, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You should see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.

After you enable the project cost budget feature, the page is refreshed, and a **Budget match priorities** tab is added.

## Create a project cost budget

To create a project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the command bar of the project's main form, select **Create Budget**, and then follow these steps:

    - To manually create the budget, select **Manual**. A **Budget** tab is added to the page and includes a blank grid for budget lines. 
    - To create budget lines, select **New Project Budget Line**.
    

For information about how to create cost budget lines, see [Project time budget lines](project-cost-time-budget-line.md), [Project material budget lines](project-cost-material-budget-line.md), and [Project expense budget lines](project-cost-expense-budget-line.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
