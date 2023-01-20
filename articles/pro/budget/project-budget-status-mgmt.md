---
title: Project budget status management
description: This article provides the stauts management of project budget.
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget status management

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Prerequisite for this article is that the project budget is created. See the article, [Create and delete project cost budgets](create-delete-project-budget.md) to understand 
how a project budget is created for a project.

This article explains the various status of project budget. What are the triggers for the status transition and explain the status in which project budget would be open for edit. 

> [!NOTE]
>Project budget needs to be in approved status, for actuals to get tracked against the project budget.



Project budget status transition would be as explained in below picture.



![Picture explaining the project budget's status transition.](../pro/budget/media/2-project-budget-state-management-pic.png)



| **Budget status** | **What does the status mean?** |
|         ---       | --- |
|       Draft     | Budget dimensions, quantity, prices, budget amounts can be updated and saved in this status. Budget needs to be submitted to move to In review status. Budget lines are editable.|
|       In Review | Budget is submitted for approval, and it is in review. Can move to Approved status if its approved or move back to Rejected status if it is rejected. Budget is not editable in this status.|
|       Approved     | Budget is approved and actuals would be tracked against the budget lines. Budget is not editable in this status.|
|       Rejected     | Budget which was submitted for review is rejected. Budget lines needs to be updated as per the user need and re-submitted to move it to In review status. Budget lines are editable in this status.|
|       Revised     | An approved budget version is revised, and a new budget version was approved. At this stage the previous approved version would move to Revised status. Budget lines are not editable in this status. |






[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
