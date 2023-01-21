---
title: Key concepts in Project budget management
description: This article explains key concepts of Project budget management in Microsoft Dynamics 365 Project Operations.
author: niranjanmaski
ms.date: 12/16/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Key concepts in Project budget management

_**Applies to:** _Lite deployment - deal to proforma invoicing._

This article explains key concepts that you should be aware of before you start to use Project budget management in Microsoft Dynamics 365 Project Operations.

### Project budget
Project budget represents a point in time snapshot of the estimated spend across the project phases and its associated tasks. Even if there's a change in prices of the resources, material, or expenses, that do not impact the budget snapshot once it's made part of the budget.

### Cost budget

Cost budget is the point in time snapshot of estimated cost for the project. All actual costs incurred on the project amongst time, material, expenses would be compared against the cost budget to track the costs spent on the project.

### Revenue budget

Revenue budget is the point in time snapshot of estimated revenue for the project. All unbilled and billed sales on the project would be compared against the revenue budget to track the revenue on the project.

### Budget line

Budget line of a project budget identifies a discrete set of dimensions on which the cost or revenue of the project needs to be tracked. Dimensions across budget lines need to be unique to ensure that actuals matching a certain dimensions would always get counted against the same budget line.

### Actual

Actual is a time entry, expense, or a material usage approved by the set workflow, which can be considered as a cost to the project.

### Budget line match priority

Budget line match priority defines the order in which the budget to actual matching logic respects various dimensions of an actual while matching against the budget lines. 

For instance, as per the default budget match priority for transaction class expense the following table shows the typical priority order in which the actual is matched.

| **Field name** | **Applicable transaction class** | **Context** | **Budget match priority** |
| --- | --- | --- | --- |
| msdyn_transactioncategory | Expense | Cost | 1 |
| msdyn_task | Expense | Cost | 2 |
| msdyn_costtype | Expense | Cost | 3 |
| msdyn_accountvendor | Expense | Cost | 4 |

The actual expense attempts to match to the budget line with maximum number of dimensions matched. 
- A budget line with msdyn_transactioncategory, msdyn_task, msdyn_costtype, and msdyn_accountvendor defined would be searched for. 
- If there's no match, the lowest priority dimension msdyn_accountvendor would be avoided in the next pass to match against a budget line. 
- If there's no match still, the next lowest priority dimension msdyn_costtype would be avoided in the next pass to match against a budget line.
- This will continue utill a unique budget line is matched or an error is encountered.

### Budget forecast

Budget forecast is the expected spend or revenue per budget line during the period defined on the budget line. The forecast is equal to the budgeted value when the budget is approved.

The forecast would be made equal to the actuals if the actuals are more than the forecast for the budget line. Because the actuals have already more than the budget, the forecast would be at least equal to the actuals.

### Variance

Variance is the difference between budgeted spend or revenue and the actual spend or revenue.

| **Budget type** | **Condition** | **Variance value** |
| --- | --- | --- |
| Cost | If actual is **less** than forecast | Zero |
| Cost | If actual is **more** than forecast | Equivalent to (actual – forecast) |
| Revenue | If actual is **more** than forecast |  Zero |
| Revenue | If actual is **less** than forecast | Equivalent to (actual – forecast) |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
