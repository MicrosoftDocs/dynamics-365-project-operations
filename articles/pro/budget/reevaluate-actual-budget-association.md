---
title: Re-evaluate cost actual to budget association 
description: This article explains how to re-evaluate actual to cost budget association. 
author: niranjanmaski
ms.date: 03/20/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Re-evaluate cost actual to budget association

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

Project cost actuals which are created against the project will go through the approval process and would be available under **Actuals** tab. Actuals tab can be
added to project page, from the **Related** entities. 

Actuals are also available under **Sales** in the left navigation, change the area to **Sales**, under Transactions in the left navigation, select **Actuals** to see
**Active Actuals** view. Filter by the **ProjectID** and add the project name you are interested to see all actuals of a particular project.

Once a project budget is created and approved as per, [budget creation](create-delete-project-budget.md) and [budget approval](project-budget-status-mgmt.md), project
cost actuals would be attempted to be matched against the approved budget lines. Matching of an actual to a budget line would follow the [budget line match priority](budget-line-match-priority.md).

The budget line to which the project cost actual is matched is available in the **Actuals** page under the tab **Budget Associations**.

## How to re-evaluate cost actuals to budget association?

1. In **Actuals** list page, in **Active Actuals** view, select the cost actuals you wish to re-evaluate.
2. **Re-evaluate Budget association** ribbon action would appear on the top of the page.
3. Click **Re-evaluate Budget association**, the actual would be scheduled for re-evaluation.
4. Other option is to click on cost actual, **Re-evaluate Budget association** ribbon action would be available, if clicked would also schedule the actual for re-evaluation.
5. Cost actual to budget matching periodic job would pick the actual for evaluation. This job runs for every 5 mins, as a default configuration.
6. To check the status, click on the cost actual, under **General** tab, two fields **Budget Evaluation Status** and **Budget Evaluation Result** will have the status. 
7. If a cost actual is associated to a budget line it is available in **Budget Associations** tab.

The following table explains how to interpret the status of the re-evaluate action.

| Budget Evaluation Status | Budget Evaluation Result | Status of actual to budget association |
|---|---|---|
| Empty | Empty | Budget is not in approved status. |
| Scheduled | Empty | Periodic job is yet to pick the actual for evaluation.  |
| Completed | Empty | Actual is associated to a budget line, can check in Budget Associations tab.  |
| Completed | Error | Error occurred during matching of actual to budget and the error is displayed here.  |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
