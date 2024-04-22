---
title: Cost and sales budget management in resource nonstocked deployment.
description: This article provides the details of how a cost and sales budgets can be managed in resource nonstocked deployment. 
author: niranjanmaski
ms.date: 04/14/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget management overview for resource nonstocked

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/nonstocked based scenarios, Lite deployment - deal to proforma invoicing._

This article provides the typical actions to performe for cost and sales budget management in a resource nonstocked deployment. 

As explained in the [project budget management overview](project-budget-management-overview-res-non-stocked.md) the project creation, actuals tracking against budget, budget approval, forecast update, and budget revision happens on the Dataverse side. Approved budgets are transferred to forecast tables in finance and operations apps. 

A project budget for tracking both costs and sales budgets can be created for all types of projects (fixed-price, time and material, and investment).

Here's the step by step process of creation and approval of project budgets in Dataverse.

| Step | Action in Dataverse | Relevant Documentation | Comments |
|---|---|---|---|
| Step 1 | Plan your project and create estimates. | Project estimates are created if you plan your tasks and assign resources. |  |
| Step 2 | Setup budget period. | [Budget period setup](../pro/budget/budget-period-setup.md) | Budget period setup is a must for time phasing.|
| Step 3 | Create project budget. | [Create cost budget](../pro/budget/create-delete-project-budget.md) and [Create sales budget](../pro/budget/create-delete-project-sales-budget.md) | If needed, you can create only a cost or a sales budget. |
| Step 4 | Summarize budget lines if needed. | [Summarize project budget lines](../pro/budget/summarize-budgetline-during-import.md) | Summarizing budget lines enables you to reduce the number of budget lines to be managed. |
| Step 5 | Add any budget lines if needed. | [Add any more budget lines ](../pro/budget/project-cost-time-budget-line.md) | If needed, add extra lines other than from estimates. |
| Step 6 | Submit the budget for review and approve budget. | [Submit and approve budget ](../pro/budget/project-budget-status-mgmt.md) | Budget needs to be approved to transfer the budget lines to forecasts in Finance and operations.  |
| Step 7 | Track the budget line against actuals and revise the budget if needed. | [Revise the budget if needed ](../pro/budget/revise-project-cost-budget.md) | If needed after revision, the budget needs to be approved. |

Once the budget is in approved state, the budget can be [transferred to forecasts in finance and operations](transfer-budgets-to-forecasts.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)

