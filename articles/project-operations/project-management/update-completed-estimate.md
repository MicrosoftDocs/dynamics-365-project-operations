---
# required metadata

title: Update estimate at completion
description: This topic provides information about updating the projection of effort on a project. 
author: ruhercul
manager: AnnBe
ms.date: 08/18/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
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

# Update estimate at completion

It's common for a project manager to revise the original estimates on a task. Project reprojections are a project manager's perception of estimates, given the current state of a project. However, we don't recommend that project managers change the baseline numbers, because the project baseline represents the established source of truth for the project's schedule and cost estimate, and all project stakeholders have agreed to it.

There are two ways that a project manager can reproject effort on tasks:

- Override the default ETC with a new estimate of the actual remaining effort on the task. 
- Override the default progress percentage with a new estimate of the true progress on the task.

Each of these approaches cause a recalculation of the task's ETC, EAC, and progress percentage, and the projected effort variance on a task. The EAC, ETC, and progress percentage on the summary tasks are also recalculated, and produce a new projection of effort variance.
