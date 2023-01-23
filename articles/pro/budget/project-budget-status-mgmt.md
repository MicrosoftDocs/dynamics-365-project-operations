---
title: Project budget status management
description: This article provides information about the status management of project budget.
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget status management

_**Applies to:** _Lite deployment - deal to proforma invoicing._

Prerequisite for this article is that the project budget is created. To understand how a project budget is created for a project, see [Create and delete project cost budgets](create-delete-project-budget.md).

This article explains the various statuses of a project budget, the triggers for the status transition, and the status in which project budget would be open for edit. 

> [!NOTE]
> Project budget needs to be in approved status, for actuals to get tracked against the project budget.



Project budget status transition are explained in the following image.

![Image explaining the project budget's status transitions.](media/2-project-budget-state-management-pic.png)



| **Budget status** | **What does the status mean?** |
|         ---       | --- |
|       Draft     | The budget dimensions, quantity, prices, and budget amounts can be updated and saved in this status. The budget needs to be submitted to move to the **In review** status. Budget lines are editable.|
|       In Review | The budget is submitted for approval, and it's in review. Can move to the **Approved** status if it's approved, or moved back to the **Rejected** status if it's rejected. The budget isn't editable in this status.|
|       Approved     | The budget is approved and the actuals are tracked against the budget lines. Teh budget isn't editable in this status.|
|       Rejected     | The budget that was submitted for review is rejected. The budget lines need to be updated by the user and then resubmitted to move it to the **In review** status. The budget lines are editable in this status.|
|       Revised     | An approved budget version is revised, and a new budget version was approved. At this stage the previously approved version is moved to the **Revised** status. The budget lines aren't editable in this status. |



## Budget approval

To approve a project budget, follow these steps.

1. Sign-in to Microsoft Dynamics 365 Project Operations.
1. From the left navigation, change the area to **Projects**.
1. Assuming that budget is created, the **Budget** tab is visible, and the budget lines are created based on the project's needs.
1. When all budget lines are created and you are ready to get it approved, select **Submit budget**. The budget status is set to **In Review**, and the budget isn't editable.
1. Select the **Budget** in the top ribbon to see the **Approve** and **Reject** options.
1. After validating the submitted budget, select **Approve** to approve the submitted budget. 
1. If you want to make changes to the budget, select **Reject** to move the budget to the *Rejected* status. You can edit the budget and submit it again for approval.
 
> [!NOTE]
> Currently there is no approval workflow implemented for budget approval. 


## Delete budget

To delete a project budget, follow these steps.

> [!NOTE]
> Budget data can't be recovered once a budget is deleted. 

1. Sign-in to Microsoft Dynamics 365 Project Operations.
1. From the left navigation, change the area to **Projects**.
1. Assuming that budget is created, the **Budget** tab is visible, and the budget lines are created based on the project's needs.
1. Select the **Budget** in the top ribbon to see the **Approve** and **Reject** options. The **Delete** option is only only available if the budget status is either **Draft** or **Rejected**. Budgets can't be deleted if the status is either **In Review**, **Approved**, or **Revised**.
1. To delete a budget, select **Delete**, and then select **Confirm**.
1. Select **Cancel**’ on the confirmation dialog to cancel the budget deletion.

> [!NOTE]
> A project with a budget can't be deleted unless the project budget is deleted.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
