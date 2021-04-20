---
# required metadata

title: Project invoice proposal performance
description: This topic provides information about performance improvements to project invoice proposals.
author: Yowelle
manager: AnnBe
ms.date: 04/20/2021
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 

# optional metadata

ms.search.form: 
# ROBOTS: 
audience: Application User, IT Pro
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: Core, Operations
# ms.tgt_pltfrm: 
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
# ms.search.industry: 
ms.author: andchoi
ms.search.validFrom: 20121-03-05
ms.dyn365.ops.version: 10.0.18

---

# Project invoice proposal performance

[!include [banner](../includes/banner.md)]

When you create a new invoice proposal you might encounter performance issues as the number of projects and subprojects increase. To improve performance, a feature is available that reduces the time needed to create a new invoice proposal for posted project transactions.

## Enable project invoice proposal performance enhancement
To enable the project invoice proposal performance enhancement feature, complete the following steps.

1.	Go to **Feature management** > **All**. In the feature list, locate **Project invoice proposal performance enhancement**.
2.	Select **Enable now**.
3.	Refresh your browser, and then create a new invoice proposal.

## Turn off project invoice proposal performance enhancement
Complete the following steps to turn off the project invoice proposal performance enhancement.

1.	Go to **Feature management** > **All**. In the feature list, locate **Project invoice proposal performance enhancement**.
2.	Select **Disable**.
3.	Refresh your browser.

> [!NOTE]
> Invoice proposal performance can't be applied when billing rules are enabled or batch processes are running.
