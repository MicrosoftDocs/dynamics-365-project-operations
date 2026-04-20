---
title: Create forecast models for project budgets 
description: Learn about how to create a forecast model for remaining budgets.
author: Yowelle
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Service industries
ms.author: andchoi
ms.dyn365.ops.version: 7.0
ms.search.validFrom: 2019-01-15
---

# Create forecast models for project budgets

[!include [banner](../includes/banner.md)]

This article describes how to create a forecast model for remaining budgets. A project that is subject to budget control uses two types of budgets: original and remaining. When you create a project budget, you must specify the original and remaining budget forecast models that you created in the **Forecast models** page. You create project budgets based on the specified models when you commit the project budget.

> [!NOTE]
> A forecast model that you use for budget control can't have a submodel or be used as a submodel.

1. Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.
1. Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.
1. Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.
1. If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**
1. To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.
1. In the **Budget type** field, select one of the following model types:

   - **Original budget**: Use the original budget amounts that you commit when you create and approve the initial budget.
   - **Remaining budget**: Use the remaining budget amounts during the life of the project. Actual transactions reduce the balances in this forecast model, and budget revisions increase or decrease them.
   - **Carry-forward**: Use the carry-forward budget amounts for the project. Carry-forward is an optional process that you can run to transfer unused budget amounts from one fiscal year to another.

1. Set the following options as required:

   - Enable **Forecast invoice date** to use the project date as the invoice date.
   - Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.
   - You can keep the default **Budget type** as **None** or enter a new type. You can't change the budget type after you change a record.

    > [!NOTE]
    > If you change the default budget type, you can't update any other options, and you can't reuse this forecast model.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
