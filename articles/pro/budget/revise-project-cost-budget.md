---
title: Revise a project cost budget
description: This article explains how to revise a project cost budget. 
author: niranjanmaski
ms.date: 03/20/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Revise a project cost budget

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how a project cost budget can be revised.

Throughout the course of project execution, actuals for time, expense, material are associated with the corresponding budget lines. 
By comparing the actuals with the budget, any variance is updated against the corresponding budget lines. Forecasts are editable in the tracking mode of the grid and can be updated to reflect the reality of the project. 

When forecasts need to be formalized as a budget, a budget revision is needed. 

> [!Note]
> A project cost budget can be revised only if the version is in **Approved** status.

To revise the project cost budget, follow these steps.

1. Sign in to Project Operations.
1. In the left navigation, change the area to **Projects** and select the project, which needs to be revised. 
1. In the **Project** page, in the **Action** pane, select **Budget**, and then select **Revise**. A confirmation dialog opens to choose the forecast values during revision of the budget. 
   - If you choose to use forecasted amounts and quantities, they'll serve as a basis for creating the revised budget amount and quantity during the revision process. You'll have the opportunity to edit them further as needed.
   - If you choose not to use forecasted amounts and quantities, the forecasts won't be considered during the revision process.
1. After selecting the **Revise** button, you'll see an information strip on the project page that indicates the budget revision is in progress.

Budget revision takes some time based on the number of budget lines involved. Wait for the **Notification** to indicate that the budget revision is completed. A new budget version is created in **Draft** status, and you can view the budget lines, which are successfully revised in the grid. To view the summary of the budget revision, check the **Timeline** section on the **Project summary** tab.
    
> [!Note]
> During revision if a budget line can't be created due to changed dependencies, the reason for the failure is logged in the error log, which is accessed from the **Timeline** section of the **Project summary** tab. By addressing these errors, you can resolve the issues and **Delete** the budget version in draft and revise again.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
