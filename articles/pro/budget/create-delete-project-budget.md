---
title: Create and delete project cost budgets
description: This article explains how to create and delete a project cost budget.
author: nimaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create and delete project cost budgets

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

## Enable the project cost budget feature

Project cost budgeting capabilities are enabled only if the feature flag is enabled.

> [!NOTE]
> After the project budget feature is enabled in an organization, it can't be disabled. However, you don't have to create a budget for every project.

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

> [!NOTE]
> Only one cost budget can be created for each project.

## Delete a project cost budget

> [!NOTE]
> A project cost budget can be deleted only if the budget is in either **Draft** or **Rejected** status. It can't be deleted if it's in **Review**, **Approved**, or **Revised** status.

To delete a project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
