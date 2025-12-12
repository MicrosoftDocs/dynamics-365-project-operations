---
title: Import an estimate to a project-based contract line
description: This article provides information about how to import estimates from a project to a contract line.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Import an estimate to a project-based contract line

_**Applies To:** Project Operations Integrated with ERP_

In Dynamics 365 Project Operations, you can import estimates from a project to a project-based contract line.

1. Verify that the **Project** field on the project-based contract line is filled in.
2. On the tab **Contract Line Details** tab, on the subgrid, select **Import from Project Estimation**. A dialog page with summarization options opens. The available summarization options are, **Transaction Class**, **Category**, **Role**, and **Project task**. Based on the selections for summarization, the estimate from the project for all of the transaction classes included on this contract line are copied over. 
3. To check what transaction classes are included, on the **General** tab of the contract line, check the values in the **Include Time**, **Include Expenses**, and **Include Fees** fields.

When you import estimates, the application defaults the pricing based on the project price lists attached to the contract and the billing type set up on the contract line. If a role or category is set up on the contract line as non-chargeable, the imported estimate line for that role or category is non-chargeable and will not add up to the contracted value of contract line.

When a contract line has line details, the **Contract Value** and the **Estimated Tax** fields on the contract line are summarized and can't be edited.

When multiple summarization options are selected, the system attempts to summarize by all of the selected options. The summarization output results in more imported contract lines than if you select only one summarization option.

For example, if the project had the following estimate lines for expenses:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

When the user selects to summarize by **Transaction Class**, the following information will be imported:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| &nbsp;  | &nbsp;  | 10/1/2020 | 3.34 | 840 | 2800 |

When the user selects to summarize by **Transaction Class** and **Category**, the following information will be imported:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| &nbsp;  | Hotel | 10/1/2020 | 6 | 200 | 1200 |

When the user selects to summarize by **Transaction Class**, **Category** and **Leaf Node Task**, the following will be imported. Notice that this result is the same as what was on the project:

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
