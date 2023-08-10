---
title: Create budget lines from unmatched actuals
description: This article explains how to create project budget lines from cost actuals that which couldn't be matched to an existing budget line during revision. 
author: niranjanmaski
ms.date: 07/25/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create budget lines from unmatched actuals

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains the process of creating budget lines from unmatched cost actuals. This situation can occur when actuals don't match existing budget lines based on dimensions or defined budget match priorities. It's also possible due to unforeseen actuals during budget creation and approval.

This feature allows users to create budget lines that correspond to unmatched cost actuals. 
This choice is available when revising an approved budget line.

## How to see cost actuals unmatched to a budget line

After a project budget is approved, all approved cost actuals related to the project undergo automatic evaluation to match with the planned budget lines. This evaluation occurs periodically. To check the status of this evaluation, you can refer to the **Budget Evaluation Status** field on the **Actual** main page.

If a cost actual fails to match with a budget line, the evaluation status shows as **Completed**, and the **Budget Evaluation Result** field displays an error message that indicates a matching budget line for the actual couldn't be found. 

To simplify the process of identifying cost actuals that don't match with budget lines, two default views have been introduced. These views help you quickly locate cost actuals that haven't been matched to an approved budget line.

To access these cost actual views, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Select **Projects** to view the list of active projects.
1. Locate and select the desired project to open the project main page.
1. If you don't find the **Actuals** tab listed, select **Related**, and then select the **Actuals** tab.
1. Within the **Actuals** tab, locate the view selector dropdown at the top of the grid.
1. Two new views are available: **Cost Actuals Matched to Budget** and **Cost Actuals Unmatched to Budget**.
1. The **Cost Actuals Unmatched to Budget** displays the list of cost actuals that haven't been matched to an approved budget line.

> [!NOTE]
> The two new views on the **Actuals** tab that show matched and unmatched actuals to budget lines are also available on the **Actuals list** page.

## Create budget lines from cost actuals unmatched to a budget line

To create a project budget line from the unmatched cost actuals, follow these steps.

> [!NOTE]
> To perform this action, ensure that the selected budget version is in the **Approved** status.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Select **Projects** to view the list of active projects.
1. Locate and select the desired project to open the project main page.
1. In the top ribbon bar select **Budget**.
1. If the budget version is in **Approved** status, you should see an option to **Revise**.
1. Select **Revise** to open a dialog box.
1. Mark the option **Create budget lines from unbudgeted actuals** as **Yes**.
1. Select **Revise** to start the revision.
1. After revision, a new budget version is created in **Draft** status.
1. The grid displays new budget lines from unbudgeted actuals alongside previous budget lines.
1. For a revision summary, review the **Timeline** section of the **Project summary** tab.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
