---
title: Reevaluate actual to budget association. 
description: This article explains how to re-evaluate actual to cost budget association. 
author: niranjanmaski
ms.date: 03/20/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Re-evaluate actual to budget association

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

Project cost actuals which are created against the project will go through the approval process and would be available under **Actuals** tab. Actuals tab can be
added to project page, from the **Related** entities. 

Actuals are also available under **Sales** in the left navigation, change the area to **Sales**, under Transactions in the left navigation, select **Actuals** to see
**All Actuals** view. Filter by the **ProjectID** and add the project name you are interested to see all actuals of a particular project.

Once a project budget is created and approved as per, [budget creation](create-delete-project-budget.md) and [budget approval](project-budget-status-mgmt.md), project
cost actuals would be attempted to be matched against the approved budget lines. Matching of an actual to a budget line would follow the [budget line match priority](budget-line-match-priority.md).

The budget line to which the project cost actual is matched is available in the **Actuals** page under the tab **Budget Associations**.

There are two options to perform re-evaluation of cost actual to budget line association.

Option 1

1. In **Actuals** list page in **All Actuals** view, select the cost actuals you wish to re-evaluate, in this view you can select multiple cost actuals.
2. **Re-evaluate Budget association** ribbon action would appear on the top of the page.
3. Click **Re-evaluate Budget association**, the actual would be scheduled for re-evaluation.
4. Cost actual to budget matching periodic job, which runs for every 5 mins, as a default configuration, would pick the actual for evaluation.
5. The result of the budget matching would be available 
6.  for next matching cycle which would take a maximum of 5 minutes.
7. To see the result of th


actuals
which are created
Select the project which needs to be revised.
Time, material, expense actuals which are raised and approved against a project would



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
