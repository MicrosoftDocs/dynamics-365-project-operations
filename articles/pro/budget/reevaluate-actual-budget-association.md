---
title: Re-evaluate cost actual to budget association 
description: This article explains how to re-evaluate actual to cost budget association. 
author: niranjanmaski
ms.date: 03/20/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Re-evaluate cost actual to budget association

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to re-evaluate cost actual to budget association.

Project cost actuals, which are created against the project, go through the approval process and are available under **Actuals** tab. The **Actuals** tab can be
added to the project page using **Related** entities. 

Actuals are also available under **Sales** in the left navigation. Change the area to **Sales** and select **Transactions** in the left navigation, and then select **Actuals** to see the **Active Actuals** view. Filter by the **ProjectID**, and add the project name you're interested in to see all actuals for the project.

Once a project budget is created and approved using either, [budget creation](create-delete-project-budget.md) and [budget approval](project-budget-status-mgmt.md), project cost actuals are matched against the approved budget lines. Matching actuals to a budget line follows the [budget line match priority](budget-line-match-priority.md).

The budget line to which the project cost actual is matched is available in the **Actuals** page on the **Budget Associations** tab.

## How to re-evaluate cost actuals to budget association

To re-evaluate cost actuals to budget association, follow these steps.

1. On the **Actuals** list page, in the **Active Actuals** view, select the cost actuals you want to re-evaluate. The **Re-evaluate Budget association** ribbon action appears on the top of the page.
1. Select **Re-evaluate Budget association**, the actual would be scheduled for re-evaluation. Another option is to select a cost actual, then the **Re-evaluate Budget association** ribbon action is available, also schedules the actual for re-evaluation. 

The cost actual to budget matching periodic job then picks up the actual for evaluation. This job runs for every 5 mins, as a default configuration. To check the status, select the cost actual, then select the **General** tab. The **Budget Evaluation Status** and the **Budget Evaluation Result** fields show the status. 

If a cost actual is associated to a budget line, it's available in **Budget Associations** tab.

The following table explains how to interpret the status of the re-evaluate action.

| Budget Evaluation Status | Budget Evaluation Result | Status of actual to budget association |
|---|---|---|
| Empty | Empty | Budget isn't in approved status. |
| Scheduled | Empty | Periodic job is yet to pick the actual for evaluation.  |
| Completed | Empty | Actual is associated to a budget line, can check in Budget Associations tab.  |
| Completed | Error | Error occurred during matching of actual to budget and the error is displayed here.  |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
