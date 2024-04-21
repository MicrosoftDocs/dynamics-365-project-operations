---
title: Cost and sales budget management in resource non-stocked deployment.
description: This article provides the details of how a cost and sales budgets can be managed in resource non-stocked deployment. 
author: niranjanmaski
ms.date: 04/14/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget management overview for resource non-stocked

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides the typical actions to be performed for cost and sales budget management in resource non-stocked deployment. 

As explained in the [project budget management overview](project-budget-management-overview-res-non-stocked.md) the project creation, actuals tracking against budget, budget approval, forecast update, budget revision happens on dataverse side. Approved budgets would be transfered to forecast tables on the Finance & Operations. 

A project budget can be created for all types of projects, fixed-price, time and material, and investment projects, for tracking both costs and sales budgets.

Here is the step by step process of creation and approval of project budgets in dataverse.

| Step | Action in Dataverse | Relavent Documentation | Comments |
|---|---|---|---|
| Step1 | Plan your project and create estimates | Project estimates are created if you plan your tasks and assign resources. |  |
| Step2 | Setup budget period | [Budget period setup](../pro/budget/budget-period-setup.md) | Budget period setup is a must for time phasing.|
| Step3 | Create project budget | [Create cost budget](../pro/budget/create-delete-project-budget.md) & [Create sales budget](../pro/budget/create-delete-project-sales-budget.md) | You can create only cost or sales budget if needed|
| Step4 | Summarize budget lines if needed | [Summarize project budget lines](../pro/budget/summarize-budgetline-during-import.md) | This would enable you reduce the number of budget lines to be managed|
| Step5 | Add any budget lines if needed | [Add any additional budget line ](../pro/budget/project-cost-time-budget-line.md) | Additional lines other than from estimates |
| Step6 | Submit the budget for review and approve budget | [Submit and approve budget ](../pro/budget/project-budget-status-mgmt.md) |  |
| Step7 | Track the budget line against actuals and revise the budget if needed | [Revise the budget if needed ](../pro/budget/revise-project-cost-budget.md) |  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)

