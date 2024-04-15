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

Capability to transfer approved budgets from dataverse to Finance and Operations is currently in public preview and you need to enable the feature **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.** in Finance and Operations feature management to be able to transfer the budgets to forecasts.

Follow the below steps to enable the feature. 
1. The capability to import approved budgets into forecasts on Finance and Operations is behind a feature, **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.**, which needs to be enabled.
1. In Finance & Operations -> System Administration -> Feature Management, please **Check for updates** in the top right corner.
1. Search for the feature name **Enable Project Budget management feature in Project Operations for non-stocked/resource based scenarios.** and Enable the feature.
1. Once this feature is succesfully enabled, you would be Import budget lines into forecasts from **All forecasts** form and also as a periodic scheduled job once the batch job is scheduled.

A project budget can be created for all types of projects, fixed-price, time and material, and investment projects, for both costs and sales budgets.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)


