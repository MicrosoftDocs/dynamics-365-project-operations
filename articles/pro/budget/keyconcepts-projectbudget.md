---
title: Key concepts in Project budget management
description: The article explains some key concepts of Project budget management in Microsoft Dynamics 365 Project Operations.
author: niranjanmaski
ms.date: 12/16/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Project budget management overview

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The article explains some key concepts that you should be aware of before you start to use Project budget management in Microsoft Dynamics 365 Project Operations.

### Budget
Project budget represents a point in time snapshot of the estimated spend across the project phases and its associated tasks. Even if there is a change in prices of the resources, material, or expenses, that donot impact the budget snapshot once it is made part of the budget.

### Cost budget

Cost budget is the point in time snapshot of estimated cost for the project. All actual costs incurred on the project amongst time, material, expenses would be compared against the cost budget to track the cost spent on the project.

### Revenue budget

Revenue budget is the point in time snapshot of estimated revenue for the project. All unbilled and billed sales on the project would be compared against the revenue budget to track the revenue on the project.

### Budget line

Budget line of a project budget identifies a discrete set of dimensions on which the cost or revenue of the project needs to be tracked. Dimensions across the budget lines needs to be unique, this is to ensure all actuals matching certain dimension would compare against the same budget line.

### Actual

Actual is a time entry, expense or a material usage approved by the set workflow, which can be considered as a cost to the project.

### Budget line match priority

Budget line match priority defines the order in which the budget to actual matching logic would respect various dimensions of actual while matching against the budget lines. 

For instance. As per the default budget match priority for transaction class expense the following would be the priority order in which the actual would be matched.

| **Field name** | **Applicable transaction class** | **Context** | **Budget match priority** |
| --- | --- | --- | --- |
| msdyn_transactioncategory | Expense | Cost | 1 |
| msdyn_task | Expense | Cost | 2 |
| msdyn_costtype | Expense | Cost | 3 |
| msdyn_accountvendor | Expense | Cost | 4 |

Actual expense would be attempted to match to the budget line with maximum number of dimensions matched. 
- A budget line with msdyn_transactioncategory, msdyn_task, msdyn_costtype, msdyn_accountvendor defined would be attempted to be matched. 
- If there is no match, the lowest priority dimension msdyn_accountvendor would be avoided in the next pass to match against a budget line. 
- If there is no match still, the next lowest priority dimension msdyn_costtype would be avoided in the next pass to match against a budget line.
- This continues till a unique budget line is matched or an error is encountered.

### Budget forecast

Budget forecast is the expected spend or revenue per budget line during the period defined in the budget line. Forecast would be equal to budgeted value when budget is approved.

Forecast would be made equal to actuals if actuals are more than forecast for the budget line. This is the forecast would be atleast equal to actuals now.

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
