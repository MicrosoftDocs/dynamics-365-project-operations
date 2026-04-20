---
title: Project stage types
description: This article provides information about project stages.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: concept-article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Project stage types 

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]

Project stages are designed to reflect the state of the project as it progresses. Customizations can be used to automatically update the stages with business process flows, Power Automate, or plug-in extensions.

The following stages are defined in the default BPF:

- New
- Quote
- Plan
- Deliver
- Complete
- Close 

## New

When you create a project, the project stage is set to **New**. If the project was created from a template, it might have schedule, estimate, and team data. Otherwise, it's just an outline of the project, and the remaining components must be entered.

## Quote

When you associate a project with a quote, or when you create a project from a quote, the project stage is set to **Quote**, and the estimated start and end dates are updated. While the project is in the **Quote** stage, the **Sales** tab on the **Project Entity** page shows details of the quote.

## Plan

When you win a quote that is associated with a project, and the project is moved to the **Contract** phase, the project stage is updated to **Plan**. While the project is in the **Plan** stage, the **Project Entity** page shows details of the contract.

## Deliver

When the project plan is completed, and you're ready to start the project, the project manager should update the project stage to **Deliver** to show that the project has started.

## Complete 

When the work for the project is completed, the project manager can update the stage to **Complete**. By updating the project stage to **Complete**, the project manager indicates that the work is 100-percent completed, but that the project is being kept open so that any pending time or expense entries can be recorded.

## Close

When all transactions are recorded for the project, the project manager can update the stage to **Close**. At that point, no transactions can be recorded, and the project is set to read-only.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
