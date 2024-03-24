---
title: Summarize budget lines during import
description: This article explains how budget lines can be summarized during import.
author: niranjanmaski
ms.date: 01/01/2024
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Summarize budget lines during import

[!INCLUDE[banner](../../includes/banner.md)]

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

You can import budget lines from different sources, such as estimates, quote line details, or contract line details. These sources may have many lines each.

For instance, if you assign all resources to tasks, you'll get an estimate for every resource. 
But you may want to track budgets at a higher level, such as the task level. 
In this case, you can use the summarizing feature when importing budget lines, and group them by task. This way, the estimates of all resources for a task form one budget line. The number of budget lines are the same as the number of tasks, which makes it easier to manage.

## How to summarize budget lines during import

Summarize option is made part of import. 

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**, and then follow these steps:

    1. Select **Import**.
    1. In the import dialog there are two sections for Summarization, one for cost budget lines and one for sales budget lines. 
    1. In **Cost budget line import options** section, choose the summarization options for Time, Expense, Material cost budget lines.
    1. In **Sales budget line import options** section, choose the summarization options for Time, Expense, Material sales budget lines.
    1. For each of the transaction class, the dimensions displayed as summarization options are as per the **Budget match priority**.
    1. If you select a lower priority match priority dimension, all other higher priority dimensions are also considered as summarized options.
    1. This mechanism would that budget lines are summarized in a way where the actual matching would be successful, which runs based on **Budget match priority**

> [!NOTE]
> Budget match priorities for both cost & sales budget lines are by default defined at project parameters level. In case budget match priorities are defined at a project level, the match priority at project would take the precedence. For more information, see the [budget match priority](budget-line-match-priority.md),  section.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
