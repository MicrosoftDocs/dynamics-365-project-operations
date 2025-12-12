---
title: Create and delete project sales budgets
description: This article explains how to create and delete a project sales budget.
author: niranjanmaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create and delete project sales budgets

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

## Enable the project sales budget feature

Project cost and sales budgeting capabilities are enabled only if the feature flag is enabled.

> [!NOTE]
> After the project budget feature is enabled in an organization, it can't be disabled. However, you don't have to create a budget for every project.

To enable project cost and sales budgeting, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You should see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.

After you enable the project cost and sales budget feature, the page is refreshed, and a **Budget match priorities** tab is added. You should see that budget match priorities were created for both the **Cost** context and the **Sales** context.

## Create a project sales budget

To create a project sales budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project's main page, on the Action Pane, select **Create Budget**.
1. To manually create the budget, select **Manual**. A **Budget** tab is added to the page. It includes a blank grid for budget lines.
1. To create budget lines, select **New Project Budget Line**.
1. In the quick create dialog box, in the **Context** field, select **Sales** to create a sales budget line.

> [!NOTE]
> Only one sales budget can be created for each project.

## Create sales budget lines

To create a project sales budget from estimates, follow the steps in [Create a project budget from estimates](create-project-budget-from-estimates.md).

To manually create sales budget lines, follow the steps in the following articles:

- [Project time budget lines](project-cost-time-budget-line.md)
- [Project material budget lines](project-cost-material-budget-line.md)
- [Project expense budget lines](project-cost-expense-budget-line.md)

## Delete a project sales budget

> [!NOTE]
> A project sales budget can be deleted only if the budget is in either **Draft** or **Rejected** status. It can't be deleted if it's in **Review**, **Approved**, or **Revised** status.

To delete a project sales budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
