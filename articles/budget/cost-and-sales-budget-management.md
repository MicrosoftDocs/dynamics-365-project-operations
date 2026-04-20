---
title: Cost and sales budget management
description: This article provides details about how cost and sales budgets can be managed in resource nonstocked deployments.
author: niranjanmaski
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Cost and sales budget management

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for Project Operations Integrated with ERP based scenarios._

This article describes the typical actions for cost and sales budget management in resource nonstocked deployments.

As outlined in [Project budget management overview for resource nonstocked](project-budget-management-overview-res-non-stocked.md), you create the project budget in Microsoft Dataverse. Therefore, you perform project creation, tracking of actuals against the budget, budget approval, forecast updates, and budget revision tasks in Dataverse. After you approve budgets, they transfer to forecast tables in finance and operations apps.

You can create a project budget for tracking both costs budgets and sales budgets for all types of projects (fixed-price, time and material, and investment).

Here's the step-by-step process for creating and approving project budgets in Dataverse.

| Step | Action in Dataverse | Relevant documentation | Comments |
|---|---|---|---|
| 1 | Plan your project, and create estimates. | | Create project estimates by planning your tasks and assigning resources. |
| 2 | Set up the budget period. | [Budget period setup](../pro/budget/budget-period-setup.md) | Set up the budget period for time phasing.|
| 3 | Create the project budget. | [Create cost budget](../pro/budget/create-delete-project-budget.md) and [Create sales budget](../pro/budget/create-delete-project-sales-budget.md) | Create only a cost budget or a sales budget, as required. |
| 4 | Summarize budget lines as required. | [Summarize project budget lines](../pro/budget/summarize-budgetline-during-import.md) | By summarizing budget lines, you reduce the number of budget lines that you must manage. |
| 5 | Add budget lines as required. | [Add any more budget lines](../pro/budget/project-cost-time-budget-line.md) | Add extra lines that don't come from estimates, as required. |
| 6 | Submit the budget for review, and approve the budget. | [Submit and approve budget ](../pro/budget/project-budget-status-mgmt.md) | Approve the budget before transferring the budget lines to forecasts in finance and operations apps. |
| 7 | Track the budget line against actuals, and revise the budget as required. | [Revise the budget if needed ](../pro/budget/revise-project-cost-budget.md) | Approve the budget after revision, as required. |

After the budget is in an approved state, you can [transfer it to forecasts in finance and operations apps](transfer-budgets-to-forecasts.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
