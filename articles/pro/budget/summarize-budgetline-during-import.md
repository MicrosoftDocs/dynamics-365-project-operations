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

For instance, if you assign all resources to tasks, you will get an estimate for every resource. 
But you may want to track budgets at a higher level, such as the task level. 
In this case, you can use the summarizing feature when importing budget lines, and group them by task. This way, the estimates of all resources for a task will form one budget line. The number of budget lines will be the same as the number of tasks, which makes it easier to manage.

## How to summarize budget lines during import

Summarize option is made part of import. 

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects**.
1. Select the project to create a budget for.
1. On the project page, on the Action Pane, select **Create Budget**, and then follow these steps:

    1. Select **Import**.
    1. In the import dialog there are two sections for Summarization, one for cost budget lines and one for sales budget lines. 
    1. In case you want to create Cost budget In the dialog there are two sections for Summarization, one for cost budget and one for sales budget. 


After the process of creating a budget from estimates is completed, a new **Budget** tab is added to the project page. A budget version is created in **Draft** status, and the grid shows the budget lines that were successfully created from estimates. For a summary of the process of creating a budget from estimates, review the **Timeline** section of the **Project summary** tab.

> [!NOTE]
> If an estimate can't be converted to a budget line, the reason for the failure is logged in the error log. You can access the error log from the **Timeline** section of the **Project summary** tab. By addressing the errors that are logged, you can fix the issues. You can then re-import the estimates. For more information, see the [Re-import estimates to create a budget](#re-import-estimates-to-create-a-budget) section.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
