---
title: Transfer budgets to forecasts
description: This article describes how to transfer budgets from Microsoft Dataverse to forecasts in finance and operations apps for resource nonstocked deployments. 
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

_**Applies To:** Project Operations for Project Operations Integrated with ERP based scenarios._

This article outlines the typical steps that are required to transfer budgets from Microsoft Dataverse to forecasts in finance and operations apps for resource nonstocked deployments.

As is outlined in [Project budget management overview for resource nonstocked](project-budget-management-overview-res-non-stocked.md), the project budget is created in Dataverse. Therefore, tasks such as project creation, tracking of actuals against the budget, budget approval, forecast updates, and budget revision occur in Dataverse. After budgets are approved, they're transferred to forecast tables in finance and operations apps.

## Enable the project budget transfer to forecasts feature

The capability to transfer approved budgets from Dataverse to finance and operations apps is currently in public preview. To enable the feature, you must activate the **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios** feature in Feature management in finance and operations apps. Additionally, if you want to periodically transfer approved budgets to forecasts, activate **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios** feature so that you can schedule the batch job.

Follow these steps to enable the feature.

1. In finance and operations apps, go to **System Administration** \> **Feature Management**, and select **Check for updates**.
1. Search for the feature that's named **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios**, and enable it.
1. After the feature is enabled, you can manually import budget lines into forecasts from the **All forecasts** page. Alternatively, you can schedule a periodic batch job to import budget lines.
1. If you want to use a batch job to periodically transfer approved budgets to forecasts, also search for and enable the feature that's named **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios**.

Project budgets can be created for different types of projects, including fixed-price, time and material, and investment projects, for both cost budgets and sales budgets.

## Manually transfer project budgets to forecasts

The capability to transfer approved budgets to forecasts is currently behind a feature. Follow the steps in the previous section to enable the **Enable Project Budget management feature in Project Operations for nonstocked/resource based scenarios** feature. Then follow these steps to manually transfer approved project budgets to forecasts.

1. In finance and operations apps, go to **Project management and accounting** \> **All Projects**.
1. On the project list page, under **Plan**, select **All forecasts**.
1. On the **All forecasts** page for the selected project, select the new **Import budget lines** button.
1. In the dialog box that appears, select the project for which you want to import approved budgets into forecasts. Then select **Import**.

    After approved budget lines are transferred to forecasts, you receive a notification.

1. Refresh the **All forecasts** page for the project to view the imported approved budget lines under the new **BUDGET** forecast model.

## Periodically transfer project budgets to forecasts

The capability to periodically transfer approved budgets to forecasts is also behind a feature. Follow the steps earlier in this article to enable the **Enable batch-schedule project budget integration from CE into F&O forecast tables for nonstocked/resource based scenarios** feature. Then follow these steps to set up the batch job that periodically transfers approved budgets to forecasts.

1. In finance and operations apps, go to **Project management and accounting** \> **Periodic** \> **Forecasts**.
1. Select the **Import approved budget lines from Dataverse into forecasts** option.
1. The batch scheduling dialog box that appears shows the **Import budget lines from Dataverse** task. Configure the batch schedule according to your requirements. This standard batch scheduling framework is from finance and operations apps.

    Budgets of all projects that have approved budget lines are transferred to forecasts in finance and operations apps according to your batch schedule.

1. If you must filter a set of projects, you can configure a filter in the **Records to include** section of the batch scheduling dialog box.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
