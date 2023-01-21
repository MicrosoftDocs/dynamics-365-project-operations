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

_**Applies to:** _Lite deployment - deal to proforma invoicing._

Prerequisite for this article is that the project budget is created. See the article, [Create and delete project cost budgets](create-delete-project-budget.md) to understand how a project budget is created for a project.

This article explains the various status of project budget. What are the triggers for the status transition and explain the status in which project budget would be open for edit. 

> [!NOTE]
>Project budget needs to be in approved status, for actuals to get tracked against the project budget.



Project budget status transition would be as explained in below picture.



![Picture explaining the project budget's status transition.](media/2-project-budget-state-management-pic.png)



| **Budget status** | **What does the status mean?** |
|         ---       | --- |
|       Draft     | Budget dimensions, quantity, prices, budget amounts can be updated and saved in this status. Budget needs to be submitted to move to In review status. Budget lines are editable.|
|       In Review | Budget is submitted for approval, and it is in review. Can move to Approved status if its approved or move back to Rejected status if it is rejected. Budget is not editable in this status.|
|       Approved     | Budget is approved and actuals would be tracked against the budget lines. Budget is not editable in this status.|
|       Rejected     | Budget which was submitted for review is rejected. Budget lines needs to be updated as per the user need and re-submitted to move it to In review status. Budget lines are editable in this status.|
|       Revised     | An approved budget version is revised, and a new budget version was approved. At this stage the previous approved version would move to Revised status. Budget lines are not editable in this status. |




## Budget approval

Follow the below steps for approving a project budget.

1.	Sign-in to Project Operations.
2.	Change area to **Projects** in left nav.
3.	Assuming that budget is created, **Budget** tab is visible and budget lines are created as per project needs.
4.	As soon as it's ensured that all budget lines are created and you wish to get it approved.
5.	Click **Submit budget** on the top ribbon. 
6.	This action would moved budget to **In Review** status and budget would be not editable.
7.	Click the **Budget** in the top ribbon, you would see options – **Approve**, **Reject**.
8.	After validating the submitted budget, click on **Approve** to approve the submitted budget. 
9.	If you want some additional changes to be done in budget, click on **Reject** in above step, which moves the budget to *Rejected* status and budget would be editable. Which can be submitted again for approval after making the needed edits.
 
> [!NOTE]
> Currently there is no approval workflow implemented for budget approval. 


## Delete budget

Follow the below steps for deleting a project budget.

> [!NOTE]
> Budget data cannot be recovered once a budget is deleted. 

1.	Sign-in to Project Operations.
2.	Change area to **Projects** in left nav.
3.	Assuming that budget is created, **Budget** tab is visible and budget lines are created as per project needs.
4.	Click the **Budget** in the top ribbon, you would see options – Approve, Reject, **Delete**.
5.	You would see **Delete** option only if the budget can be deleted as per the budget status. 
6.	Budget can be deleted only if budget is in either *Draft* or *Rejected* status. Budget cannot be deleted if budget is in *In Review*, *Approved* or *Revised* status.
7.	To delete a budget, Click **Delete** option and click **Confirm** on the confirmation dialog, if you really want to delete the budget.
8.	Clicking **Cancel**’ on the confirmation dialog would cancel the budget deletion.

> [!NOTE]
> A project with a budget cannot be deleted unless the project budget is deleted.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
