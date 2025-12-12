---
title: Create a project budget from estimates
description: This article explains how to create a project budget from estimates.
author: niranjanmaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create a project budget from estimates

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

[!INCLUDE[banner](../../includes/banner.md)]

This article explains how to create a project budget from estimates.

## Enable the project budget feature

Project budgeting capabilities are enabled only if the feature flag is enabled.

> [!NOTE]
> After the project budget feature is enabled in an organization, it can't be disabled. However, you don't have to create a budget for every project.

To enable project budgeting, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You should see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.

After you enable the project cost budget feature, the page is refreshed, and a **Budget match priorities** tab is added.

## Create a budget from estimates

You plan projects by defining tasks, assigning resources, and estimating material and expense costs. This setup is reflected in the estimates for the project, which can be viewed on the **Estimates** tab of the project page.

When these steps are followed, well-planned estimates can be used as the foundation for creating a project cost and sales budget.

> [!NOTE]
> The steps that are outlined in this article apply to both cost budget and sales budget.
>
> The action of creating a budget from estimates runs on a best-effort basis. In other words, all estimates that pass budget-related validations are created as budget lines.
> 
> The **Timeline** section of the **Project summary** tab provides a summary of the action of creating a budget from estimates.

To create a budget from estimates, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**, and then follow these steps:

    1. Select **From estimates**.
    1. In the **Time source** field, select the source for the budget lines for the **Time** transaction class:

        - To create **Time** budget lines based on the resources that are assigned to the tasks, select **Resource Assignments**. You can view these estimates on the **Resource Assignments** tab of the project page.
        - To create **Time** budget lines based on the resources that are made part of project team members, select **Project team members**. You can view these estimates on the **Team** tab of the project page.

    1. In the **Contingency** section, specify the percentage by which to increase the **Time**, **Material**, and **Expense** budget lines as contingency. The contingency amount for each budget line is calculated as a percentage of the budgeted amount and added to the budgeted amount for that line.
    1. Select **Import**. A message bar on the project page indicates that the process of creating a budget from estimates is in progress. The time that's required depends on the number of estimates that are involved. Wait until you're notified that the process is completed.

After the process of creating a budget from estimates is completed, a new **Budget** tab is added to the project page. A budget version is created in **Draft** status, and the grid shows the budget lines that were successfully created from estimates. For a summary of the process of creating a budget from estimates, review the **Timeline** section of the **Project summary** tab.

> [!NOTE]
> If an estimate can't be converted to a budget line, the reason for the failure is logged in the error log. You can access the error log from the **Timeline** section of the **Project summary** tab. By addressing the errors that are logged, you can fix the issues. You can then reimport the estimates. For more information, see the [Reimport estimates to create a budget](#reimport-estimates-to-create-a-budget) section.

After a budget is created from estimates, you can make any required edits in the grid and also add any new budget lines, just as when you manually create a budget.

For information about how to create more cost budget lines, see [Project time budget lines](project-cost-time-budget-line.md), [Project material budget lines](project-cost-material-budget-line.md), and [Project expense budget lines](project-cost-expense-budget-line.md).

## Reimport estimates to create a budget

If errors occur during the process of creating a budget from estimates, you can make the required changes to the estimates to address the errors. You can then try to re-create the budget from estimates.

> [!IMPORTANT]
> If you reimport estimates to create a budget, the budget is deleted and re-created. Any changes that were made to the budget are overwritten.

> [!NOTE]
> You can reimport estimates only if the budget is in **Draft** status.

To reimport estimates to create a budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to reimport estimates to create a budget.
1. On the project page, select **Budget**, and then select **Reimport estimates**.
1. A message box notifies you that a reimport of estimates deletes all budget lines and re-creates the budget from estimates. Select **OK** to confirm that you want to reimport estimates.
1. In the **Import from estimates** dialog box, follow the steps in the [Create a budget from estimates](#create-a-budget-from-estimates) section.

## Delete a project budget

> [!NOTE]
> A project budget can be deleted only if the budget is in either **Draft** or **Rejected** status. It can't be deleted if it's in **Review**, **Approved**, or **Revised** status.

To delete a project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
