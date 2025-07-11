---
title: What's new June 2021 - Project Operations Core deployment
description: This article provides information about the quality updates available in the June 2021 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new June 2021 - Project Operations Core deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.11.0.156 or 4.11.0.164.

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2281417 | Fixed the issue regarding the failure of the automatic invoice creation action through the invoice schedule. |
| Billing and Pricing | 2287835 | 	Improved invoice confirmation performance. |
| Opportunity Management | 2222555 | Material estimates chargeability must be correctly copied to quote line details when using **Import from Project Estimation**. |
| Opportunity Management | 2223427 | Customizations are now allowed for the action, **GenerateRetainersFromRetainerScheduleOptions**. |
| Opportunity Management | 2277528 | Fixed billing milestone value calculation for project contract lines with multiple customers. |
| Project Planning and Tracking | 2226110 | Fixed the intermittent issue with the **Generate Requirement** function in the **Project team** grid. |
| Project Planning and Tracking | 2208109 | Users can't create a project in one currency with related tasks in another currency. |
| Project Planning and Tracking | 2258228 | The list of fields allowed to modify with **Scheduling** entities using the Schedule API has been updated. |
| Project Planning and Tracking | 2293989 | The correct language and regional settings must be passed to the **Project Tasks** grid.|
| Resource Management | 2220493 | Fixed the user experience in the **Task** grid when quickly marking a resource request as complete. |
| Resource Management | 2330496 | Fixed the **Schedule Board** loading issue. (Quality update is available in version 4.11.0.164) |
| Time and Expense | 2194431 | The **Time entry** grid must honor the start of the week as set in the **System settings**. |
| Time and Expense | 2277311 | After you delete the value in a cell in the **Time entry** grid, the cursor remains in the grid. |
