---
title: Revise a project cost budget
description: This article explains how to revise a project cost budget.
author: niranjanmaski
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Revise a project cost budget

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

This article explains how to revise a project cost budget.

During the course of project execution, you associate actuals for time, expenses, and materials with corresponding budget lines. By comparing the actuals with the budget, you can update any variance against the corresponding budget lines. When the grid is in tracking mode, you can update forecasts to reflect the reality of the project.

When you must formalize forecasts as a budget, a budget revision is required.

> [!NOTE]
> You can revise a project cost budget only if the version is in **Approved** status.

To revise a project cost budget, follow these steps:

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project that you want to revise.
1. On the **Project** page, on the Action Pane, select **Budget**, and then select **Revise**. A message box prompts you to select the forecast values during revision of the budget.

    - If you choose to use forecasted amounts and quantities, they serve as the basis for creating the revised budget amount and quantity during the revision process. You can edit them further, as required.
    - If you choose not to use forecasted amounts and quantities, the forecasts aren't considered during the revision process.

1. Select **Revise**. A message bar on the project page indicates that the budget revision is in progress. The time that the process requires depends on the number of budget lines that are involved. Wait until you're notified that the budget revision is completed.

After the budget revision is completed, a new budget version is created in **Draft** status, and the grid shows the budget lines that were successfully revised. For a summary of the budget revision, review the **Timeline** section of the **Project summary** tab.

> [!NOTE]
> During revision, if a budget line can't be created because of changed dependencies, the reason for the failure is logged in the error log. You can access the error log from the **Timeline** section of the **Project summary** tab. By addressing the errors that are logged, you can fix the issues. You can then delete the budget version in **Draft** status and revise the budget again.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
