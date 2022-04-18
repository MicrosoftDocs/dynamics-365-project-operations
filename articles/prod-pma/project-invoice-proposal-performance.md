---
# required metadata

title: Project invoice proposal performance
description: This topic provides information about performance improvements to project invoice proposals.
author: Yowelle
ms.date: 06/16/2021
ms.topic: article
ms.prod: 
ms.technology: 

# optional metadata

ms.search.form: 
# ROBOTS: 
audience: Application User, IT Pro
# ms.devlang: 
ms.reviewer: johnmichalak
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
> Invoice proposal performance can't be applied when billing rules are enabled.
> 
> During the batch process to create invoice proposals, the number of subtasks will split the tasks to a maximum number based on the number of contracts with invoiceable transactions, regardless of what you have entered. For example, if you enter **3** for the number of subtasks for invoice proposal creation in batch, and there are only two contracts with invoiceable transactions, only two subtasks are created.
