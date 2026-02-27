---
title: Create budget lines from unmatched actuals
description: This article explains how to create project budget lines from cost actuals that could not be matched to an existing budget line during revision.
author: nniranjanmaski
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Create budget lines from unmatched actuals

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains the process of creating budget lines from unmatched cost actuals. You might need to use this process when actuals don't match existing budget lines, based on dimensions or defined budget match priorities. You might also need to use it because of unforeseen actuals during budget creation and approval.

This feature enables users to create budget lines that correspond to unmatched cost actuals. This option is available when you revise an approved budget line.

## How to identify cost actuals that aren't matched to a budget line

After a project budget is approved, automatic evaluation is periodically done to match all approved project-related cost actuals to the planned budget lines. To determine the status of this evaluation, review the **Budget Evaluation Status** field on the **Actual** main page.

If a cost actual can't be matched to a budget line, the evaluation status is **Completed**, and the **Budget Evaluation Result** field shows an error message that indicates that a matching budget line could not be found for the actual.

To help you quickly and easily find cost actuals that haven't been matched to an approved budget line, two default views have been introduced: **Cost Actuals Matched to Budget** and **Cost Actuals Unmatched to Budget**. Follow these steps to access the new views on the project main page.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the **Actuals** tab, find the view selector (dropdown menu) above the grid. Notice that it includes the two new views: **Cost Actuals Matched to Budget** and **Cost Actuals Unmatched to Budget**.

    > [!TIP]
    > If the **Actuals** tab isn't shown, select **Related**, and then select the **Actuals** tab.

1. To view the list of cost actuals that haven't been matched to an approved budget line, select the **Cost Actuals Unmatched to Budget** view in the view selector.

> [!NOTE]
> The two new views are also available on the **Actuals list** page.

## Create budget lines from cost actuals that aren't matched to a budget line

To create a project budget line from the unmatched cost actuals, follow these steps:

> [!NOTE]
> Before you complete this procedure, ensure that the budget version is in **Approved** status.

1. Sign in to Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the Action Pane, select **Budget**.

    If the budget version is in **Approved** status, a **Revise** option should be available.

1. Select **Revise** to open a dialog box.
1. Set the **Create budget lines from unbudgeted actuals** option to **Yes**.
1. Select **Revise** to start the revision.

    After the revision is completed, a new budget version is created in **Draft** status. The grid shows new budget lines from unbudgeted actuals alongside previous budget lines.

1. For a revision summary, review the **Timeline** section of the **Project summary** tab.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
