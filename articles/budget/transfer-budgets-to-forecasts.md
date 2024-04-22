---
title: Transfer budgets to forecasts
description: This article details the process of transferring budgets from Dataverse to forecasts in finance and operations apps for resource nonstocked deployment. 
author: niranjanmaski
ms.date: 04/14/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Transfer budgets to forecasts

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/nonstocked based scenarios, Lite deployment - deal to proforma invoicing._

This article outlines the typical steps involved in transferring budgets from Dataverse to forecasts in finance and operations apps for resource nonstocked deployment.

As outlined in the [project budget management overview](project-budget-management-overview-res-non-stocked.md), project budget is created in Dataverse. So, the tasks such as project creation, tracking actuals against budget, budget approval, forecast updates, and budget revisions take place within Dataverse. Following approval, the budgets are then transferred to forecast tables within finance and operations apps.

## Enable the project budget transfer to forecasts feature

The capability to transfer approved budgets from Dataverse to finance and operations apps is currently in public preview. To enable this feature, you need to activate **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios** in finance and operations apps feature management. Additionally, if you wish to periodically transfer approved budgets into forecasts, you can activate **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios** to schedule the batch job.

Here are the steps to enable the feature:
1. Go to finance and operations apps and select **System Administration** -> **Feature Management** -> **Check for updates**.
1. Search for the feature name **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios**, and enable it.
1. Once enabled, you can import budget lines manually into forecasts from the **All forecasts** form, or schedule a periodic batch job to do so.
1. If you choose to transfer approved budgets into forecasts periodically using a batch job, also enable the feature **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios**.

Project budgets can be created for various project types, including fixed-price, time and material, and investment projects, covering both cost and sales budgets.

## Transfer project budget to forecasts manually

The capability to transfer approved budgets to forecasts is currently behind a feature. Follow the steps mentioned to enable the feature **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios**.

Here are the steps to manually transfer approved project budgets to forecasts:

1. Go to finance and operations apps and select **Project management and accounting** -> **All Projects**.
1. In the projects list page, under **Plan**, select **All forecasts**.
1. The **All forecasts** page for the selected project opens, where you find a new action called **Import budget lines**.
1. Select the action, and a form opens where you can select the project for which you want to import the approved budgets to forecasts. Select **Import**. You'll receive a notification after the successful transfer of approved budget lines to forecasts.
1. Refresh the **All forecasts** page of the project to view the imported approved budget lines under the new forecast model **BUDGET**.


## Transfer project budget to forecasts periodically

The capability to periodically transfer approved budgets to forecasts is also behind a feature. Follow thees steps to enable the feature **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios**.

1. Go to finance and operations apps and select **Project management and accounting** -> **Periodic** -> **Forecasts**.
1. Select the option **Import approved budget lines from Dataverse into forecasts**.
1. A batch scheduling form opens with the task **Import budget lines from Dataverse**.
1. Configure the batch schedule according to your requirements. This standard batch scheduling framework is from finance and operations apps.
1. As per your batch schedule, budgets of all projects with approved budget lines are transferred to forecasts in finance and operations apps.
1. If you need to filter a set of projects, you can configure in the **Records to include** section of the batch scheduling form.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
