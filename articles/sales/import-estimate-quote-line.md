---
title: Import estimates for a project to a project quote line
description: This article provides information about importing estimates from a project to a project quote line.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Import estimates for a project to a project quote line

_**Applies To:** Project Operations Integrated with ERP_

If you create a project during the pre-sales stage, you can import the financial estimate from the project to the project-based quote line.

1. Make sure that the project-based quote line has the project information in the **Project** field.
1. On the **Quote line details** tab, select **Import from Project Estimation**.
1. On the dialog box, select one of the following summarization options:

- **Transaction class**
- **Category**
- **Role**
- **Project task**

Based on your selection, the estimate from the project for all transaction classes included on this quote line is copied over. To check what transaction classes are included, select the **General** tab on the project-based quote line, and check the values for **Include Time**, **Include Expenses**, and **Include Fees**.

When you import estimates, the system defaults pricing based on the project price lists attached to the quote and the billing type set up on the project-based quote line. If you set up a role or category on the project-based quote line as non-chargeable, the imported estimate line is non-chargeable and doesn't add to the quoted value of quote line.

When a quote line has line details, the **Quote Value** and the **Estimated Tax** fields on the quote line are summarized and can't be edited.

When you select multiple summarization options, the system attempts to summarize by all selected options. The result is that the output of imported quote lines is more than if you selected only one summarization option.

For example, if the project has the following estimate lines for expenses.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

When the user selects to summarize by Transaction class, the following information is imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| | | 10/1/2020 | 3.34 | 840 | 2800 |

When the user selects to summarize by Transaction class and Category, the following information is imported.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| | Hotel | 10/1/2020 | 6 | 200 | 1200 |

When the user selects to summarize by Transaction class, Category, and Leaf Node Task, the following information is imported. Notice that this result is the same as what was on the project.

| Task | Category | Date | Quantity | Unit price | Amount |
| --- | --- | --- | --- | --- | --- |
| Task A | Airfare | 10/1/2020 | 4 | 400 | 1600 |
| Task B | Hotel | 10/1/2020 | 4 | 200 | 800 |
| Task C | Hotel | 11/1/2020 | 2 | 200 | 400 |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
