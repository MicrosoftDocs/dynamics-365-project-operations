---
title: What's new April 2023 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the April 2023 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: ramagadu
ms.date: 04/03/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new April 2023 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.62.0.83

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Project Accounting | **Project cost budget management**</br>This major release includes significant improvements to project cost budget management, which are accessible through a feature flag. </br> </br> In addition to manual budget line creation, users can now: </br>1. Generate budget lines from project estimates. </br>2. Track variances and update forecasts within the budget grid. </br> 3. Revise budgets as needed. </br> </br>A few known issues related to budget management. These include: </br>1. If the budget grid fails to load or budget lines are not visible, try refreshing the browser.</br> 2. To execute state change actions on the budget from the top ribbon, users need to be on the Budget tab. Otherwise, a transient error may appear. | [Project budget management overview](/dynamics365/project-operations/pro/budget/projectbudgetmanagement) |

## Quality updates
| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2904555|Block updates to Intercompany and Owning Company pricing dimensions.|
|Opportunity Management|3194606|Unable to Revise Quote with Write-in Material quote line details.|
|Project Operations Upgrade|3236820|The upgrade from version 3.x to 4.x is unsuccessful because of dependencies on other solutions.|
|Project Operations Upgrade|3264007|PSA to PO upgrade may fail on solution import at adding fields to ProductPriceLevel.|
|Project Planning and Tracking|3118566|PostProjectCreate plugin must check for Primary Requirement before Creating one.|
|Subcontracting|3106796|Can attach Time-base subcontract line to Product-Based Order line.|
|Subcontracting|3196083|Material Subcontract Lines are not defaulting product unit & unit group as per subcontracting price list.|
