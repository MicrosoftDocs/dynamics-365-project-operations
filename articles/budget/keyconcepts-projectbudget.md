---
title: Key concepts in Project budget management
description: The article explains some key concepts of Project budget management in Microsoft Dynamics 365 Project Operations.
author: niranjanmaski
ms.date: 16/12/2022
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

