---
title: Create a project budget from an estimate
description: This article explains how to create a project budget from an estimate.
author: niranjanmaski
ms.date: 03/15/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create a project budget from an estimate

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to create a project budget from estimates.

## Enable the project cost budget feature

Project cost budgeting capabilities are enabled only if the feature flag is enabled.

> [!Note]
> After the project budget feature is enabled in an organization, it can't be disabled. However, you don't have to create a budget for every project.

To enable project cost budgeting, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You should see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.

After you enable the project cost budget feature, the page is refreshed, and a **Budget match priorities** tab is added.

## Create a budget from an estimate

Projects are planned by defining tasks, assigning resources, and estimating material and expense costs. This is reflected in the estimates of the project, which can be referred to under **Estimates** tab, in the project's page. 

By following these steps, well-planned estimates can be used as the foundation for creating a project cost budget. This can be accomplished by creating the budget from estimates. 

> [!Note]
> Creating a budget from estimate will be executed on a best effort basis, which means that all estimates that pass budget-related validations will be created as budget lines. 
> 
> **Timeline** section in the project **Summary** page will provide a summary of the creating budget from estimates action. 

To create a budget from an estimate, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**, and then follow these steps:
   1. Select **From estimates**. 
   1. Select the source for the time transaction class budget lines and specify the contingency percentage for all budget lines.
      - If you want to create time budget lines based on the resources assigned to the tasks, from the **Time source** drop-down, select **Resource Assignments**. You can see these estimates under **Resource Assignments** tab on the project page. 
      - If you want to create time budget lines based on the resources made part of project team members, from the **Time source** drop-down, select **Project team members**. You can see these under **Team** tab on the project page. 
   1. In the **Contingency** section of the dialog box, indicate the percentage by which you would like to increase the **Time**, **Material**, and **Expense** budget lines as contingency. The contingency amount for each budget line is calculated as a percentage of the budgeted amount and added to the budgeted amount for that line.
   1. After selecting the **Import** button, you'll see an information strip on the project page that indicates the budget creation from estimates is in progress. Budget creation takes some time depending on the number of estimates involved, wait until the **Notification** indicates that the budget creation from estimates is complete. 

After the budget creation from estimates process is complete, a new **Budget** tab is added to the project page. A budget version will be created in **Draft** status, and you can view the budget lines, which are successfully created from estimates in the grid. To view the summary of the budget creation from estimates process, check the **Timeline** section on the project summary tab.
    
> [!Note]
> If an estimate can't be converted into a budget line, the reason for the failure is logged in the error log, which is accessed from the **Timeline** section of the project summary tab. By addressing these errors, you can resolve the issues and re-import the estimates.
    
After creation of budget from estimates, you can make any necessary edits in the grid and can also add any new budget lines, just as you would when creating a budget manually.

For information about how to create more cost budget lines, see [Project budget lines – Time](project-cost-time-budget-line.md), [Material](project-cost-material-budget-line.md), [Expense](project-cost-expense-budget-line.md)


## Re-importing estimates to create budget

If there are errors during creation of budget from estimates, you can make the necessary changes to the estimates to address the errors, and then attempt to re-create the budget from estimates.

> [!Important]
> Re-importing estimates to create a budget will result in the deletion and recreation of the budget, and any changes made to the budget will be overwritten.

> [!Note]
> Re-importing estimates is enabled only if the budget is in **Draft** status.

To re-import estimates to create a budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to re-import estimates to create budget.
1. On the project page, select **Budget**, and then select **Reimport estimates**.
1. A confirmation dialog opens to confirm if you want to reimport estimates, as it would delete all budget lines and recreate budget from estimates.
1. Click **OK** to reimport. This opens the **Import from estimates** dialog and you can follow the steps mentioned in the section [Create a budget from an estimate](create-project-budget-from-estimates.md#create-a-budget-from-an-estimate)


## Delete a project cost budget

> [!Note]
> A project cost budget can be deleted only if the budget is in either **Draft** or **Rejected** status. It can't be deleted if it's in **Review**, **Approved**, or **Revised** status.

To delete a project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
