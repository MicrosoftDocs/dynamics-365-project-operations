---
title: Import estimates from a project to a project quote line 
description: This article provides information about how to import estimates from a project to a project quote line.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Import estimates from a project to a project quote line 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing, Project Operations Integrated with ERP_

If a project is created during the pre-sales stage, you can select to import the financial estimate from the project to the project-based quote line.

1. Make sure that the project-based quote line has the project information in the **Project** field.
2. On the **Quote line details** tab, select **Import from Project Estimation**.
3. On the dialog page opens, select one of the following summarization options.

  - **Transaction class**
  - **Category**
  - **Role** 
  - **Project task**

Based on your selection, the estimate from the project for all transaction classes included on this quote line are copied over. To check what transaction classes are included, select the **General** tab on the project-based quote line, and check the values for **Include Time**, **Include Expenses**, **Include Materials**, and **Include Fees**.  To check what tasks are included, select the **Chargeable Tasks** tab on the quote line.

Depending on the Tasks associated and Included transaction classes, the estimates for those task and transaction class combinations are imported to the quote line.

When you import estimates, the system will default the pricing based on the project price lists attached to the quote and the billing type set up on the project-based quote line. If a task, role, or category is set up on the project-based quote line as non-chargeable, the imported estimate line will set as non-chargeable and won't add up to the quoted value of quote line.

When a quote line has line details, the **Quote Value** and the **Estimated Tax** fields on the quote line are summarized and can't be edited.

When multiple summarization options are selected, the system attempts to summarize by all selected options. The result is that the output of imported quote lines will be more than if you selected only one summarization option.

For example, if the project had the following estimate lines for expenses.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

When the user selects to summarize by Transaction class, the following information will be imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
|||10/1/2020 | 3.34 | 840 | 2800 |

When the user selects to summarize by Transaction class and Category, the following information will be imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| | Hotel | 10/1/2020 | 6 | 200 | 1200 |

When the user selects to summarize by Transaction class, Category and Leaf Node Task, the following information will be imported. Notice that this result is the same as what was on the project.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
