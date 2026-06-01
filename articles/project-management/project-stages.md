---
title: Project stages
description: This article provides information about the project stages that are available in Microsoft Dynamics Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project stages

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Project stages reflect the state of the project as it progresses. You can customize the project stages to automatically update with business process flows, Power Automate, or plug-in extensions.

The default business process flow defines the following stages:

- New
- Quote
- Plan
- Deliver
- Complete
- Close 

## New

When you create a project, the project stage is set to **New**. If you create the project from a template, it might have schedule, estimate, and team data. Otherwise, it's an outline of the project, and you must enter the remaining components.

## Quote

When you associate a project with a quote, or when you create a project from a quote, the project stage is set to **Quote**, and the estimated start and end dates are updated. While the project is in the **Quote** stage, the **Sales** tab on the **Project Entity** page shows details of the quote.

## Plan

When you win a quote that you associated with a project, and you move the project to the **Contract** phase, the project stage updates to **Plan**. While the project is in the **Plan** stage, the **Sales** tab on the **Project Entity** page shows details of the contract.

## Deliver

When the project plan is completed, and you're ready to start the project, the project manager should update the project stage to **Deliver** to show that the project has started.

## Complete 

When the work for the project is completed, the project manager can update the stage to **Complete**. By updating the project stage to **Complete**, the project manager indicates that the work is 100-percent completed, but that the project is being kept open so that any pending time or expense entries can be recorded.

## Close

When all transactions are recorded for the project, the project manager can update the stage to **Close**. At that point, no transactions can be recorded, and the project is set to read-only.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
