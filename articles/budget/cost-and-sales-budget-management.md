---
title: Cost and sales budget management
description: This article provides details about how cost and sales budgets can be managed in resource nonstocked deployments.
author: niranjanmaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Cost and sales budget management

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for Project Operations Integrated with ERP based scenarios._

This article describes the typical actions that are performed for cost and sales budget management in resource nonstocked deployments.

As is outlined in [Project budget management overview for resource nonstocked](project-budget-management-overview-res-non-stocked.md), the project budget is created in Microsoft Dataverse. Therefore, tasks such as project creation, tracking of actuals against the budget, budget approval, forecast updates, and budget revision occur in Dataverse. After budgets are approved, they're transferred to forecast tables in finance and operations apps.

A project budget for tracking both costs budgets and sales budgets can be created for all types of projects (fixed-price, time and material, and investment).

Here's the step-by-step process for creating and approving project budgets in Dataverse.

| Step | Action in Dataverse | Relevant documentation | Comments |
|---|---|---|---|
| 1 | Plan your project, and create estimates. | | Project estimates are created if you plan your tasks and assign resources. |
| 2 | Set up the budget period. | [Budget period setup](../pro/budget/budget-period-setup.md) | Budget period setup is necessary for time phasing.|
| 3 | Create the project budget. | [Create cost budget](../pro/budget/create-delete-project-budget.md) and [Create sales budget](../pro/budget/create-delete-project-sales-budget.md) | As required, you can create only a cost budget or a sales budget. |
| 4 | Summarize budget lines as required. | [Summarize project budget lines](../pro/budget/summarize-budgetline-during-import.md) | By summarizing budget lines, you can reduce the number of budget lines that must be managed. |
| 5 | Add budget lines as required. | [Add any more budget lines](../pro/budget/project-cost-time-budget-line.md) | As required, add extra lines that don't come from estimates. |
| 6 | Submit the budget for review, and approve the budget. | [Submit and approve budget ](../pro/budget/project-budget-status-mgmt.md) | The budget must be approved before the budget lines can be transferred to forecasts in finance and operations apps. |
| 7 | Track the budget line against actuals, and revise the budget as required. | [Revise the budget if needed ](../pro/budget/revise-project-cost-budget.md) | As required after revision, the budget must be approved. |

After the budget is in an approved state, it can be [transferred to forecasts in finance and operations apps](transfer-budgets-to-forecasts.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
