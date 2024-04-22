---
title: Project budget management overview for resource nonstocked
description: This article provides an overview of project budget management in resource nonstocked deployment.
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

This article provides an overview of the end-to-end project budget management process in project-based organizations, this article covers in the context of resource nonstocked deployment.

In a project, each phase, task, or work package incurs costs as labor, materials, and expenses. A project budget represents a point-in-time snapshot of the estimated spend across the project phases and its associated tasks. 

Similar to project editing capabilities, in a resource nonstocked deployment, budget creation, approval, and revision happens on the project form of Dataverse environment. 

Check out the Lite deployment's documentation regarding [project budget management](../pro/budget/projectbudgetmanagement.md) to get an overview of all actions that can be performed on project budget in Dataverse. 

## Project budget management in Microsoft Dynamics 365 Project Operations

Project budget management typically follows the business process flow shown in the following illustration.

![Business process flow for project budget management in Project Operations.](media/1-Budgetmanagementoverviewresourcenonstocked.png)

Here's a step-by-step description of the project budget management process.

1. Below steps to be performed on the Dataverse.
1. The project manager creates a budget for a project. The project budget can be created either from scratch or by using the project estimates of the project as input.
1. The project manager can budget for the **Time**, **Material**, or **Expense** transaction class for the different phases of the project.
1. The project manager submits the project budget for approval. An optional workflow for project budget approval can be enabled according to business requirements.
1. If the project budget is approved, all actuals created and approved for time, materials, and expenses are matched against the project budget lines. Actual budget consumption and forecasts are automatically updated, and any variance between the budget and actuals is shown.
1. The project manager periodically reviews the project budget and checks for variance between the budget and actuals.
1. As required, the project manager updates the forecasts, based on the actual consumption during project execution.
1. If extra budget is allocated to the project, or if the contract is updated due to spending, the project manager may choose to revise the budget accordingly to align with the updated forecasts.
1. The revised project budget follows the project budget approval workflow. After the project is approved, a new version of the project budget is used for the comparison of the budget versus actuals.
1. Below steps to be performed on the Finance & Operations.
1. The capability to import approved budgets into forecasts on Finance and Operations is behind a feature, **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios.**, which needs to be enabled.
1. Follow the steps explained [here](transfer-budgets-to-forecasts.md#enable-project-budget-transfer-to-forecasts-feature) to enable the feature. 
1. Once this feature is successfully enabled, you would be able to Import budget lines into forecasts from **All forecasts** and also as a periodic scheduled job once the batch job is scheduled.  
   

A project budget can be created for all types of projects, fixed-price, time and material, and investment projects, for both costs and sales budgets.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
