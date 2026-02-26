---
title: Create and delete project cost budgets
description: This article explains how to create and delete a project cost budget.
author: nimaski
ms.date: 02/26/2026
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

You can enable project cost budgeting capabilities by turning on the feature flag.

> [!NOTE]
> After you enable the project budget feature in an organization, you can't disable it. However, you don't need to create a budget for every project.

To enable project cost budgeting, follow these steps:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.

After you enable the project cost budget feature, the page refreshes, and a **Budget match priorities** tab is added.

## Create a project cost budget

To create a project cost budget, follow these steps:

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the command bar of the project's main form, select **Create Budget**, and then follow these steps:

    - Select **Manual** to manually create the budget. A **Budget** tab is added to the page and includes a blank grid for budget lines. 
    - Select **New Project Budget Line** to create budget lines.
    

For information about how to create cost budget lines, see [Project time budget lines](project-cost-time-budget-line.md), [Project material budget lines](project-cost-material-budget-line.md), and [Project expense budget lines](project-cost-expense-budget-line.md).

> [!NOTE]
> You can create only one cost budget for each project.

## Delete a project cost budget

> [!NOTE]
> You can delete a project cost budget only if the budget is in **Draft** or **Rejected** status. You can't delete the budget if it's in **Review**, **Approved**, or **Revised** status.

To delete a project cost budget, follow these steps:

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
