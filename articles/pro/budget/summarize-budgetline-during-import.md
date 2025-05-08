---
title: Summarize budget lines during import
description: This article explains how budget lines can be summarized during import.
author: niranjanmaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Summarize budget lines during import

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

You can import budget lines from different sources, such as estimates, quote line details, or contract line details. Each of these sources can have many lines.

For example, if you assign all resources to tasks, you get an estimate for every resource. However, you might want to track budgets at a higher level, such as the task level. In this case, you can use the summarization feature when you import budget lines, and group them by task. In this way, the estimates of all resources for a task form one budget line. Because the number of budget lines equals the number of tasks, management is easier.

## Summarize budget lines during the import process

Summarization options are available as part of the import process. Follow these steps to summarize budget lines during import.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**.
1. Select **Import**.

    The import dialog box that appears has two sections for **Summarization**: one for cost budget lines and one for sales budget lines.

1. In the **Cost budget line import options** section, select the summarization options for **Time**, **Expense**, and **Material** cost budget lines.
1. In the **Sales budget line import options** section, select the summarization options for **Time**, **Expense**, and **Material** sales budget lines.

For each transaction class, the dimensions that appear as summarization options are based on the budget match priority. If you select a lower-priority match priority dimension, all higher-priority dimensions are also considered summarized options.

Budget lines are summarized in such a way that the actual matching that runs based on the budget match priority is successful.

> [!NOTE]
> By default, budget match priorities for both cost budget lines and sales budget lines are defined at the project parameter level. Any budget match priorities that are defined at the project level take the precedence. For more information, see [Budget line match priority](budget-line-match-priority.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
