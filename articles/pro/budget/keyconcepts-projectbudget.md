---
title: Key concepts in project budget management
description: This article explains key concepts of project budget management in Microsoft Dynamics 365 Project Operations.
author: nimaski
ms.date: 06/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Key concepts in project budget management

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

This article explains key concepts that you should be aware of before you start to use project budget management in Microsoft Dynamics 365 Project Operations.

## Project budget

A project budget represents a point-in-time snapshot of the estimated spend across the project phases and its associated tasks. Even if the prices of the resources, materials, or expenses change, the changes don't affect the budget snapshot after it's made part of the budget.

## Cost budget

A cost budget represents a point-in-time snapshot of estimated cost for the project. All actual costs that are incurred on the project among time, materials, and expenses are compared against the cost budget, to track the costs on the project.

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
