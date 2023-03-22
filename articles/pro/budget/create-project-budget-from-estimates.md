---
title: Create a project budget from estimates
description: This article explains how to create a project budget from estimates.
author: niranjanmaski
ms.date: 03/15/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create a project budget from estimates

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

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

## Creating budget from estimates

Projects are planned by defining tasks, assigning resources, and estimating material and expense costs. This is reflected in the estimates of the project which can be referred under **Estimates** tab, in the project's page. 

By following these steps, a well-planned estimates can be used as the foundation for creating a project cost budget. This can be accomplished by creating the budget from estimates. 

> [!NOTE]
> Creating a budget from estimates will be executed on a best effort basis, which means that all estimates that pass budget-related validations will be created as budget lines. 
> 
> **Timeline** section in the project **Summary** page will display a summary of the create budget from estimates process, including any error logs for estimates that could not be created as budget lines.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**, and then follow these steps:

    - Select **From estimates**. 
    
    - A dialog box will open, allowing you to choose the source for the time transaction class budget lines and specify the contingency percentage for all budget lines.
    
    - In the drop down for Time source, select **Resource Assignments** if you want to create time budget lines based on the resources assigned to the tasks. You can see these estimates under **Resource Assignments** tab in the project page. 
    
    - In the drop down for Time source, select **Project team members** if you want to create time budget lines based on the resources made part of project team members. You can see these under **Team** tab in the project page. 
    
    - In the **Contingency** section of the dialog box, indicate the percentage by which you would like to increase the Time, Material, and Expense budget lines as contingency.
    
    - The contingency amount for each budget line will be calculated as a percentage of the budgeted amount and added to the budgeted amount for that line.
    
    - Upon clicking the **Import** button, you will see an information strip on the project page indicating that the budget creation from estimates is in progress.
         
    - Budget creation would take some time based on number of estimates involved, wait for the **Notification** to indicate that the budget creation from estimates is completed.
    
    - After the budget creation from estimates process is complete, a new **Budget** tab will be added to the project page. 
    
    - A budget version will be created in **Draft** status, and you can view the budget lines which are successfully created from estimates in the grid.
    
    - To view the summary of the budget creation from estimates process, check the **Timeline** section on the project summary tab.
    
       
After creation of budget from estimates, you can make any necessary edits in the grid and can also add any new budget lines, just as you would when creating a budget manually.

For information about how to create additional cost budget lines, see [Project budget lines – Time](project-cost-time-budget-line.md), [Material](project-cost-material-budget-line.md), [Expense](project-cost-expense-budget-line.md)


## Re-importing estimates to create budget

In case there are errors during creation of budget from estimates, you can make the necessary changes to the estimates to address the errors, and then attempt to re-create the budget from estimates.

> [!NOTE]
> Re-importing estimates to create a budget will result in the deletion and recreation of the budget, and any changes made to the budget will be overwritten.

> [!NOTE]
> Re-importing estimates would be enabled only if the budget is in **Draft** status.

To re-import estimates to create a budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to re-import estimates to create budget.
1. On the project page, select **Budget**, and then select **Reimport estimates**.
1. A confirmation dialog will open to confirm if you want to reimport estimates as it would delete all budget lines and recreate from estimates.
1. Click **OK** to reimport. This would open the **Import from estimates** dialog and follow the steps mentioned in the section [Create budget from estimates](create-project-budget-from-estimates.md#creating-budget-from-estimates)




## Delete a project cost budget

> [!NOTE]
> A project cost budget can be deleted only if the budget is in either **Draft** or **Rejected** status. It can't be deleted if it's in **Review**, **Approved**, or **Revised** status.

To delete a project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
