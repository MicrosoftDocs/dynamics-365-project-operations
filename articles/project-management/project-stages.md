---
# required metadata

title: Project stages
description: This article provides information about the project stages that are available in Microsoft Dynamics Project Operations.
author: ruhercul
ms.date: 09/18/2020
ms.topic: article
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Project stages

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project stages are designed to reflect the state of the project as it progresses. Customizations can be used to automatically update the stages with business process flows, Power Automate, or plug-in extensions.

The following stages are defined in the default business process flow:

- New
- Quote
- Plan
- Deliver
- Complete
- Close 

## New

When you create a project, the project stage is set to **New**. If the project was created from a template, it might have schedule, estimate, and team data. Otherwise, it's an outline of the project, and the remaining components must be entered.

## Quote

When you associate a project with a quote, or when you create a project from a quote, the project stage is set to **Quote**, and the estimated start and end dates are updated. While the project is in the **Quote** stage, the **Sales** tab on the **Project Entity** page shows details of the quote.

## Plan

When you win a quote that is associated with a project, and the project is moved to the **Contract** phase, the project stage is updated to **Plan**. While the project is in the **Plan** stage, the **Sales** tab on the **Project Entity** page shows details of the contract.

## Deliver

When the project plan is completed, and you're ready to start the project, the project manager should update the project stage to **Deliver** to show that the project has started.

## Complete 

When the work for the project is completed, the project manager can update the stage to **Complete**. By updating the project stage to **Complete**, the project manager indicates that the work is 100-percent completed, but that the project is being kept open so that any pending time or expense entries can be recorded.

## Close

When all transactions are recorded for the project, the project manager can update the stage to **Close**. At that point, no transactions can be recorded, and the project is set to read-only.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
