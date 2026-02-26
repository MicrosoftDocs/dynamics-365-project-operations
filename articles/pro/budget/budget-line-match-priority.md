---
title: Budget line match priority
description: This article explains how budget line match priority works for project budgets.
author: niranjanmaski
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Budget line match priority

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Budget line match priority defines the order in which an actual cost matches against the different dimensions of budget lines.

As part of the solution update that includes project budgeting, the system creates the Budget line match priority table.

You enable the project budget feature by using a feature flag. For more information, see [Enable the project cost budget feature](create-delete-project-budget.md#enable-the-project-cost-budget-feature).

> [!NOTE]
> After you enable the project budget feature in an organization, you can't disable it. However, you don't have to create a budget for every project.

After you enable the feature flag, the **Budget match priorities** tab appears on the project parameters main page. This tab shows the following default rows that are applicable for the **Time**, **Expense**, and **Material** transaction classes in the context of a class.

| Field name | Applicable transaction class | Context | Budget match priority |
|---|---|---|---|
| msdyn\_unitschedule | Expense | Cost | 0 |
| msdyn\_task | Expense | Cost | 10 |
| msdyn\_transactioncategory | Expense | Cost | 20 |
| msdyn\_costtype | Expense | Cost | 30 |
| msdyn\_accountvendor | Expense | Cost | 40 |
| msdyn\_unitschedule | Material | Cost | 0 |
| msdyn\_task | Material | Cost | 10 |
| msdyn\_product | Material | Cost | 20 |
| msdyn\_writeinproductdescription | Material | Cost | 30 |
| msdyn\_costtype | Material | Cost |40 |
| msdyn\_accountvendor | Material | Cost | 50 |
| msdyn\_unitschedule | Time | Cost | 0 |
| msdyn\_task | Time | Cost | 10 |
| msdyn\_resourcecategory | Time | Cost | 20 |
| msdyn\_resourceorganizationalunitid | Time | Cost | 30 |
| msdyn\_bookableresource | Time | Cost | 40 |
| msdyn\_costtype | Time | Cost | 50 |
| msdyn\_accountvendor | Time | Cost | 60 |
| msdyn\_unitschedule | Expense | Sales | 0 |
| msdyn\_task | Expense | Sales | 10 |
| msdyn\_transactioncategory | Expense | Sales | 20 |
| msdyn\_unitschedule | Material | Sales | 0 |
| msdyn\_task | Material | Sales | 10 |
| msdyn\_product | Material | Sales | 20 |
| msdyn\_writeinproductdescription | Material | Sales | 30 |
| msdyn\_unitschedule | Time | Sales | 0 |
| msdyn\_task | Time | Sales | 10 |
| msdyn\_resourcecategory | Time | Sales | 20 |
| msdyn\_resourceorganizationalunitid | Time | Sales | 30 |
| msdyn\_bookableresource | Time | Sales | 40 |

> [!NOTE]
> The msydn_unitschedule field with the display name Unit Group is a match priority that you can't update or delete. This match priority ensures that the unit match and conversion happens in the right way.

## How does budget match priority work?

Time entry, expense entry, or material use is submitted against a project for approval. After it's approved, it's considered an approved actual that's used in project cost and sales budgeting calculations.

Actuals have dimensions that define an actual. Here are some examples:

- The task that the actual is created against
- The role of the resource that's submitting the time entry
- The name of the material that's used
- A flight expense that's billed against a project
- A time entry from a subcontractor that's approved by a project manager

When actuals are posted against a project, they must be mapped to the correct budget lines. This mapping is done by matching the dimensions of incoming actuals with the dimensions of all budget lines in the cost budget. An actual is matched to the budget line that matches most of its dimensions.

During matching, the order that the matching algorithm works in is defined by the Budget line match priority table.

Priority 1 is the highest priority for dimensions of a transaction class. The algorithm tries to match all dimensions of an actual against all budget lines.

If no match is found and no error is encountered, the matching algorithm skips the *lowest-priority dimension*, according to the budget line match priority table, and attempts another match. This process is repeated until a match is found or an error occurs. If multiple budget lines match an actual, this situation is considered an error.

### Example

This example shows how the process works for an expense that's posted against a project. The following table shows the priority order in which the actual is matched for an expense if the default budget match priority is used.

| Field name | Applicable transaction class | Context | Budget match priority |
|---|---|---|---|
| msdyn\_transactioncategory | Expense | Cost | 1 |
| msdyn\_task | Expense | Cost | 2 |
| msdyn\_costtype | Expense | Cost | 3 |
| msdyn\_accountvendor | Expense | Cost | 4 |

The actual expense is matched to the budget line where the largest number of dimensions is matched.

1. The matching algorithm tries to match a budget line where **msdyn\_transactioncategory**, **msdyn\_task**, **msdyn\_costtype**, and **msdyn\_accountvendor** are defined.
1. If there's no match, the lowest-priority dimension, **msdyn\_accountvendor**, is avoided in the next attempt to match against a budget line.
1. If there still is no match, the next-lowest-priority dimension, **msdyn\_costtype**, is avoided in the next attempt to match against a budget line.
1. The process continues until a unique budget line is matched or an error is encountered.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
