---
title: Creatie and delete project cost budgets
description: This article provides the details for how to create and delete a project cost budget.
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create and delete project cost budgets

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

## Enable the project cost budget feature

The project cost budget feature is enabled using a feature flag. All project cost budgeting capabilities are enabled only if feature flag is enabled.

To enable project cost budgeting, follow these steps.

1. Sign-in to Microsoft Dynamics 365 Project Operations.
1. From the left navigation, change the area to **Settings**.
1. In the **General section, select **Parameters**. You will see list of **Organization Units**. 
1. Double-click the **Organization Units** row on the columns that are not links. 
1. On the **Project Parameters** page, from the **Feature Control** drop-down list, select **Feature Control**.
1. Select **Enable Project Budgeting Feature Flag**.
 
After enabling the project budgeting feature, the page refreshes and a the **Budget Match Priorities** tab is created.

> [!NOTE]
> Once the project budget feature is enabled in an organization, it is not possible to disable. However, you don't have to create a budget for every project.

## Create a project cost budget

To create a project cost budget,  follow these steps. 

1. Sign-in to Project Operations.
1. From the left navigation, change the area to **Projects**. 
1. Select the project you wish to create a budget for.  
1. On the project page, select **Create Budget** in the top ribbon.  
1. Select how you wish to create the budget – **Manual** or **From estimates**.

   - When **Manual** is selected, a **Budget** tab is created with empty rows in a grid.
     - To create budget lines, select **+ New Project Budget Line**.
   - When **From estimates** is selected, you can choose the source estimates for time.
     - A new **Budget** tab is created with time, material, expense estimates pre-filled from the project estimates.
     - Select **+ New Project Budget Line** if you wish to create additional budget lines.
     - The grid and values are editable until the project budget is **Submitted for approval**.
   
For information about creating cost budget lines, see [Project budget line – Time, Material, Expense](project-budget-line.md).  

Only one cost and one revenue budget can be created for a project.

## Delete a project cost budget

To delete a project cost budget, follow these steps. 

> [!NOTE]
> A project cost budget can be deleted only if the budget is in either the **Draft** or **Rejected** status. Project budget **can't** be deleted if it is in the **Review**, **Approved**, or **Revised** status.

1. Sign-in to Project Operations.
1. From the left navigation, change the area to **Projects**.
1. Select the project you wish to delete the budget for.
1. On the project page, select **Budget**, and then select **Delete**.
  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)

