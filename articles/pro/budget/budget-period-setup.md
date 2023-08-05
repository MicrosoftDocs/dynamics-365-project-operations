---
title: Budget period setup
description: This article explains how to setup the budget period at an organization level and also at a project level. Budget period setup is a pre-requisite for time phasing.
author: niranjanmaski
ms.date: 25/08/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Budget period setup

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to setup a budget period setup, both at an organization level and also at a project level. 

## What is Budget period

Budget period would define how you would define the week, month, quarter and fiscal periods in your organization. For example, in some countries fiscal and quarter 1 would start on 01st of April and in some countries it would start on 1st of January. In some countries a work week would start on Monday and in some it would start on Sunday. 
Budget period setup at organization level would be available for consumption at a project level. However based on a specific project needs a project manager can override the organization budget period config at a project level, to cater to a specific project needs. 

## Budget period setup at Organization level

To setup a budget period at an organization level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. In the left navigation, change the area to **Settings**.
1. In the **General** section, select **Organizational Units**.
1. You should see a list of active organizational units.
1. Click the organizational unit for which you wanted to setup the budget period.
1. In the organizational unit main form, you would see a tab **Budget Period**.
1. Click the **Budget Period** tab.
1. Under the **Budget Period** tab, if you donot see an existing budget period in the grid, Click **+ New Budget Period**.
1. Click on **Save & Close**.
1. You would see a budget period line created in the grid.
1. Double click on the budget period line to open the budget period main form and see the budget period details.
1. You can edit the budget period config by updating any of the fields and clicking **Save** or **Save&Close** in the top ribbon bar.
1. Based on the configuration update, the budget period detail line would be either extended or deleted and created again.
   


> [!NOTE]
> After the project budget feature is enabled in an organization, it can't be disabled. However, you don't have to create a budget for every project.
## Revenue budget

A revenue budget represents a point-in-time snapshot of estimated revenue for the project. All unbilled and billed sales on the project are compared against the revenue budget, to track the revenue on the project.

## Budget line

A budget line of a project budget identifies a discrete set of dimensions that the cost or revenue of the project must be tracked on. Dimensions across budget lines must be unique to ensure that actuals that match a specific dimension are always counted against the same budget line.

## Actual

An actual is a time entry, expense, or a material use that's approved by defined workflow. This is the cost to the project.

## Budget line match priority

Budget line match priority defines the order in which the budget-to-actual matching logic respects the different dimensions of an actual, while it matches against the budget lines.

For example, the following table shows the typical priority order that the actual is matched, if the default budget match priority for the **Expense** transaction class is used.

| Field name | Applicable transaction class | Context | Budget match priority |
|---|---|---|---|
| msdyn\_transactioncategory | Expense | Cost | 1 |
| msdyn\_task | Expense | Cost | 2 |
| msdyn\_costtype | Expense | Cost | 3 |
| msdyn\_accountvendor | Expense | Cost | 4 |

The logic tries to match the actual expense to a budget line with most number of dimensions matched.

1. A budget line where **msdyn\_transactioncategory**, **msdyn\_task**, **msdyn\_costtype**, and **msdyn\_accountvendor** are defined is searched for.
1. If there's no match, the lowest-priority dimension, **msdyn\_accountvendor**, is avoided in the next attempt to match against all budget lines.
1. If there's no match, the next-lowest-priority dimension, **msdyn\_costtype**, is avoided in the next attempt to match against all budget lines.
1. The process continues until a unique budget line is matched or an error is encountered.

## Budget forecast

A budget forecast is the expected spend or revenue per budget line during the period that's defined on the budget line. The forecast equals the budgeted value when the budget is approved.

 If actual costs are more than the forecasted cost for a budget line, the forecast cost will be made equal to the actual cost. This is due to the fact that actuals already have more than the budget, the forecast will be at least equal to the actuals.

## Variance

Variance is the difference between the budgeted spend or revenue and the actual spend or revenue.

| Budget type | Condition | Variance value |
|---|---|---|
| Cost | The actual is **less** than the forecast. | 0 (zero) |
| Cost | The actual is **more** than the forecast. | *Variance* = *Actual* – *Forecast* |
| Revenue | The actual is **more** than the forecast. | 0 (zero) |
| Revenue | The actual is **less** than the forecast. | *Variance* = *Actual* – *Forecast* |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
