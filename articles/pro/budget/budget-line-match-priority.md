---
title: Budget line match priority
description: This article provides the details for how the project budget line match priority works. 
author: niranjanmaski
ms.date: 01/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Budget line match priority

**_Applies To:_** _Lite deployment - deal to proforma invoicing_

Budget line match priority defines the order in which an actual would be attempted to match against the various dimensions of budget lines.

As part of solution update with project budgeting, a new table **Budget line match priority** with the following default rows filled is created in the solution.
> [!NOTE]
> Once a budget feature is enabled in an organization, it is not possible to be disable. However, creating a budget for a project is as per your choice once feature is enabled.

If project budgeting feature flag is enabled as per, ['Enable the project cost budget feature'](create-delete-project-budget.md#enable-the-project-cost-budget-feature), you would see a **Budget match priorities tab** in project parameters main page.

Budget match priorities tab would show following default rows applicable for Time, Material, Expense transaction class in the context of class.

| **Field Name** | **Applicable Transaction Class** | **Context** | **Budget match priority** |
| --- | --- | --- | --- |
| msdyn\_transactioncategory | Expense | Cost | 1 |
| msdyn\_task | Expense | Cost | 2 |
| msdyn\_costtype | Expense | Cost | 3 |
| msdyn\_accountvendor | Expense | Cost | 4 |
| msdyn\_product | Material | Cost | 1 |
| msdyn\_writeinproductdescription | Material | Cost | 2 |
| msdyn\_task | Material | Cost | 3 |
| msdyn\_costtype | Material | Cost | 4 |
| msdyn\_accountvendor | Material | Cost | 5 |
| msdyn\_resourcecategory | Time | Cost | 1 |
| msdyn\_resourceorganizationalunitid | Time | Cost | 2 |
| msdyn\_bookableresource | Time | Cost | 3 |
| msdyn\_task | Time | Cost | 4 |
| msdyn\_costtype | Time | Cost | 5 |
| msdyn\_accountvendor | Time | Cost | 6 |

## How does a budget match priority work?

Time entry, expense entry or a material usage is submitted against a project for approval. Once they are approved, it would be considered as an approved actual which can be considered for project cost budgeting calculations.

Actual would have dimensions which defines an actual for example,

- Task against which the actual is created.
- Role of the resource submitting the time entry.
- Name of the material used.
- Flight expense billed against a project.
- Time entry from a subcontractor approved by a project manager.

As actuals get posted against a project, they need to be mapped to a right budget line. 
This is done by matching the dimensions of incoming actual with that of all budget lines in the cost budget.

An actual would be attempted to match to a budget line which matches to most of the dimensions on an actual. 
While matching, the order in which the matching algorithm would work is defined by the budget line match priority table.

Priority 1 is the highest priority dimension for a transaction class. 
Algorithm tries to match all dimensions of an actual against all budget lines. 

If a match is not found and no error is encountered, the matching algorithm would avoid the *least priority dimension* as per the budget line match priority table and
attempts a match again. This would continue till a match is found, or an error is encountered. 
Finding more than one budget line matching an actual is also considered as an error. 

Let us take an example how this would work for a posted expense against a project. 
As per the default budget match priority, the following would be the priority order in which the actual would be matched for an expense.

| **Field Name** | **Applicable Transaction Class** | **Context** | **Budget match priority** |
| --- | --- | --- | --- |
| msdyn\_transactioncategory | Expense | Cost | 1 |
| msdyn\_task | Expense | Cost | 2 |
| msdyn\_costtype | Expense | Cost | 3 |
| msdyn\_accountvendor | Expense | Cost | 4 |

Actual expense would be attempted to match to the budget line with maximum number of dimensions matched.

- A budget line with msdyn\_transactioncategory, msdyn\_task, msdyn\_costtype, msdyn\_accountvendor defined would be attempted to be matched.
- If there is no match, the lowest priority dimension msdyn\_accountvendor would be avoided in the next pass to match against a budget line.
- If there is no match still, the next lowest priority dimension msdyn\_costtype would be avoided in the next pass to match against a budget line. 
- This continues till a unique budget line is matched or an error is encountered.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
