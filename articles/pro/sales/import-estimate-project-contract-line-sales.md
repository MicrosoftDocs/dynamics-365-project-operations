---
title: Import estimates from a project to a project contract line
description: This article provides information about importing financial estimates from a project to a contract line.
author: poojafandan
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Import estimates from a project to a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

In Dynamics 365 Project Operations, you can import estimates from a project to a project-based contract line.

1. Verify that the **Project** field on the project-based contract line is filled in.
1. On the **Contract Line Details** tab, in the subgrid, select **Import from Project Estimation**. A dialog box with summarization options opens. Available summarization options are **Transaction Class**, **Category**, **Role**, and **Project Task**.
1. Based on the summary selection, the estimate from the project for all the transaction classes and tasks included on this contract line are copied. To check what transaction classes are included, on the **General** tab on the project-based contract line, check the values in the **Include Time**, **Include Expenses**, and **Include Fees** fields. 
1. To see what tasks are included, select the **Chargeable Tasks** tab on the contract line. Based on the associated tasks that have the field **Included Transaction Classes** set to **Yes**, all estimates for those task and transaction class combinations are imported to the contract line.

When you import estimates, the system defaults pricing based on the project price lists attached to the contract and billing type setup on the contract line. If you set up a task, role, or category on the contract line as nonchargeable, the imported estimate line is nonchargeable and doesn't add up to the contracted value of the contract line.

When a contract line has line details, the **Contract Value** and **Estimated Tax** fields on the contract line are summarized and can't be edited.

When you select multiple summarization options, the system attempts to summarize by all of the selected options. The summarization output results in more imported contract lines than if you select only one summarization option.

For example, if the project has the following estimate lines for expenses:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

When you select to summarize by **Transaction Class**, the following information is imported:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| &nbsp; | &nbsp; | 10/1/2020 | 3.34 | 840 | 2800 |

When you select to summarize by **Transaction Class** and **Category**, the following information is imported:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| &nbsp;| Hotel | 10/1/2020 | 6 | 200 | 1200 |

When you select to summarize by **Transaction Class**, **Category**, and **Leaf Node Task**, the following information is imported. Notice that this result is the same as what is on the project:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
