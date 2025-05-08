---
title: What's new October 2023 - Project Operations Lite deployment
description: This article provides information about the quality updates that are available in the October 2023 release of Microsoft Dynamics 365 Project Operations Lite deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new October 2023 - Project Operations Lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.87.0.188.

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3509236|Contract price list update doesn't affect line details.|
|Billing and Pricing|3523321|Null reference exception in GetConvertedAmountForBusinessTransaction function.|
|Billing and Pricing|3568745|Fix price list prices delete plugin by using GetTargetEntityFromEntityReference|
|Project Management|3514899|Revision token mismatch issue due to suppressed error causing transaction to be invalid.|
|Project Operations Upgrade|3546437|Error deleting task after upgrade if there's a customization on the relation between Task and Assignment.|
|Project Operations Upgrade|3551934|Orgs with Tasks and Assignments with no Project or Task linked in 3x should be blocked from upgrade to 4x and forced to clean up.|
|Project Operations Upgrade|3564488|Time out running PSA to PO upgrade data validation scripts.|
|Project Operations Upgrade|3589267|Create mitigation script to force fix affected relationships post 3x to 4x upgrade.|
|Time and Expense|3366683|Nonworking day pop-up displayed for time entries submitted on working days.|
