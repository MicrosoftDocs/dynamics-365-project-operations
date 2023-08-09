---
title: Create budget lines from unmatched actuals
description: This article explains how to create project budget lines from cost actuals which could not be matched to an existing budget lines during revision. 
author: niranjanmaski
ms.date: 28/07/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create budget lines from unmatched actuals

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article outlines the process of creating budget lines from unmatched cost actuals. This can occur when actuals don't match existing budget lines based 
on dimensions or defined budget match priorities. It's also possible due to unforeseen actuals during budget creation and approval.

This feature allows users to create budget lines that correspond to unmatched cost actuals. 
This choice is available when revising an approved budget line.

## How to see cost actuals unmatched to a budget line

After a project budget is approved, all approved cost actuals related to the project undergo automatic evaluation to match with the planned budget lines. 
This evaluation occurs periodically. To check the status of this evaluation, you can refer to the **Budget Evaluation Status** field on the Actual main form.

If a cost actual fails to match with a budget line, the evaluation status will show as **Completed**, and the **Budget Evaluation Result** field will display an error message 
indicating that a matching budget line for the actual could not be found. 

To simplify the process of identifying cost actuals that do not match with budget lines, two default views have been introduced. These views help users quickly locate cost actuals 
that have not been matched to an approved budget line.

Here's how to access these cost actual views:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Locate and click on the desired project to open the project main form.
1. If you don't find the **Actuals** tab listed, click on **Related** and then select the Actuals tab.
1. Within the Actuals tab, find the view selector drop-down at the top of the grid.
1. Two new views will be available: **Cost Actuals Matched to Budget** and **Cost Actuals Unmatched to Budget**.
1. The **Cost Actuals Unmatched to Budget** view will display the list of cost actuals that haven't been matched to an approved budget line.

> [!NOTE]
> Two new views on Actuals showing matched and unmatched actuals to budget lines are also available on the Actuals list page.
> 

## Create budget lines from cost actuals unmatched to a budget line

To create a project budget line from the unmatched cost actuals, follow these steps.

> [!NOTE]
> To perform this action, ensure that the selected budget version is in the Approved status.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Locate and click on the desired project to open the project main form.
1. In the top ribbon bar click on the **Budget**
1. Assuming that the budget version is in **Approved** status, you should see an option to **Revise**.
1. Click on Revise to open a dialog box.
1. Mark the option **Create budget lines from unbudgeted actuals** as **Yes**
1. Click on **Revise** to start the revision.
1. After revision, a new budget version is created in **Draft** status
1. The grid displays new budget lines from unbudgeted actuals alongside previous budget lines.
1. For a revision summary, review the **Timeline** section of the **Project summary** tab.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
