---
title: Project budget management overview
description: This article provides an overview of project budget management.
author: nimaski
ms.date: 02/26/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget management overview

[!INCLUDE[banner](../../includes/banner.md)]

**_Applies to:_** _Core deployment - deal to proforma invoicing._

This article provides an overview of the end-to-end project budget management process in project-based organizations.

In a project, each phase, task, or work package incurs costs as labor, materials, and expenses. A project budget represents a point-in-time snapshot of the estimated spend across the project phases and its associated tasks.

## Project budget management in Microsoft Dynamics 365 Project Operations

Project budget management typically follows the business process flow that's shown in the following illustration.

:::image type="content" source="media/1-project-budget-management-overview-pic.png" alt-text="Screenshot of the business process flow for project budget management in Project Operations.":::

Here's a step-by-step description of the project budget management process.

1. The project manager creates a budget for a project. The project budget can be created either from scratch or by using the project estimates of the project as input.
1. The project manager can budget for the **Time**, **Material**, or **Expense** transaction class for the different phases of the project.
1. The project manager submits the project budget for approval. An optional workflow for project budget approval can be enabled according to business requirements.
1. If the project budget is approved, all actuals that have been created for time, materials, and expenses are matched against the project budget lines. Actual budget consumption and forecasts are automatically updated, and any variance between the budget and actuals is shown.
1. The project manager periodically reviews the project budget and checks for variance between the budget and actuals.
1. As required, the project manager updates the forecasts, based on the actual consumption during project execution.
1. If additional budget is allocated to the project, or if the contract is updated based on spend, the project manager might decide to revise the budget so that it reflects the new forecasts.
1. The revised project budget follows the project budget approval workflow. After the project is approved, a new version of the project budget is used for the comparison of the budget versus actuals.

A project budget can be created for all types of projects, fixed-price, time and material, and investment projects.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
