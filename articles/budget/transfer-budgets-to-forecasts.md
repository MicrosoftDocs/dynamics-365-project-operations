---
title: Transfer budgets to forecasts
description: This article provides the details of how a transfer budgets in dataverse to forecasts in finance and operations in resource non-stocked deployment. 
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

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides the typical actions to be performed for transfering budgets in dataverse to forecasts in finance and operations in resource non-stocked deployment. 

As explained in the [project budget management overview](project-budget-management-overview-res-non-stocked.md) the project creation, actuals tracking against budget, budget approval, forecast update, budget revision happens on dataverse side. Approved budgets would be transfered to forecast tables on the Finance & Operations. 

## Enable project budget transfer to forecasts feature

Capability to transfer approved budgets from dataverse to Finance and Operations is currently in public preview and you need to enable the feature **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.** in Finance and Operations feature management to be able to transfer the budgets to forecasts. In case you want to enable the transfer of approved into forecasts periodically, enable the feature **Enable batch-schedule project budget integration from CE into F&O forecast tables for non-stocked/resource based scenarios.** to schedule the batch job which transfers the approved budgets into forecasts.

Follow the below steps to enable the feature. 
1. The capability to import approved budgets into forecasts on Finance and Operations is behind a feature, **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.**, which needs to be enabled.
1. In Finance & Operations -> System Administration -> Feature Management, please **Check for updates** in the top right corner.
1. Search for the feature name **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.** and Enable the feature.
1. Once this feature is succesfully enabled, you would be Import budget lines manually, into forecasts from **All forecasts** form.
 and also as a periodic scheduled job once the batch job is scheduled.
1. If you want to transfer the approved budgets into forecasts periodically using a batch job, enable the feature  **Enable batch-schedule project budget integration from CE into F&O forecast tables for non-stocked/resource based scenarios.**.

A project budget can be created for all types of projects, fixed-price, time and material, and investment projects, for both costs and sales budgets.

## Transfer project budget to forecasts manually

The capability to transfer approved budgets to forecasts is currently behind a feature, please follow the steps above to enable the same.

Follow the below steps to transfer approved project budgets to forecasts.
1. In Finance & Operations -> Project management and accounting -> All Projects
1. In the projects list page, under **Plan** select the **All forecasts**
1. All forecasts page for the selected project would open, where there is a new Forecast action available **Import budget lines**
1. A form would open up where you can select the project for which you want to import the approved budgets to forecasts and click **Import**
1. You would be notified after the succesful transfer of approved budget lines to forecast.
1. **Refresh** the All forecasts page of the project to view the imported approved budget lines into forecasts under the new forecast model **BUDGET**.

## Transfer project budget to forecasts periodically

The capability to transfer approved budgets periodically to forecasts is currently behind a feature, please follow the steps above to enable the same.

Follow the below steps to periodically transfer approved project budgets to forecasts.
1. In Finance & Operations -> Project management and accounting -> Periodic -> Forecasts
1. Select the option **Import approved budget lines from dataverse into forecasts**
1. This would open the batch scheduling form for the task **Import budget lines from dataverse**
1. Configure the batch schedule as per your needs.
1. This is a standard batch scheduling framework of Finance and Operations.
1. As per your batch schedule budgets of all projects which has approved budget lines would be transfered to forecasts in Finance and Operations.
1. In case you need to filter a set of projects, you can configure the same in **Records to include** section of the batch scheduling form.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)


