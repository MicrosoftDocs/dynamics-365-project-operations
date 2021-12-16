---
title: Expense itemization
description: 
author: suvaidya
ms.date: 12/16/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: suvaidya
---

# Expense itemization

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Organizations often require employees to provide a detailed breakdown of expenses incurred during travel. For example, a hotel folio may contain several itemized lines for room rate, tax, parking, and other miscellaneous expenses incurred each day during the duration of stay. Or, a meal expense may require that you provide a more granular breakdown for breakfast, lunch, or dinner. Whatever the needs of the organization, each expense category can be set up to reflect the subcategories or the line items that make up an expense. While itemization has always been supported in **Expense management**, the **Reimagined expense** workspace enables more efficient itemization when the feature, **Ability to itemize recurring expenses quickly** is enabled.  

## Enable quick itemization 

You can use the **Ability to itemize recurring expenses quickly** feature to itemize recurring expenses quickly while avoiding the need to enter the daily expenses each time for the duration of stay. Complete the following steps to enable quick itemization.

1. Go to the **Feature Management** workspace and in the list of features, locate and select, **Expense Reports Reimagined**. 
2. Select **Enable now**. 
3. In the feature list, locate and select, **Ability to itemize recurring expenses quickly**.
4. Select **Enable now**. 

## Itemization grid 

If an expense category has subcategories, then these expenses can be itemized. To itemize an expense, select the expense line in the expense report, and in the **Expense details** pane, select **Actions** > **Itemize**. The **Itemization** slider reveals a grid with fields. The following table provides an example of each field in the grid and how the field is rendered in the expense report. 

|     Field          |     Description                                                                                  |     Examples             |
|--------------------|--------------------------------------------------------------------------------------------------|--------------------------|
|     Subcategory    |     The list of subcategories configured under the expense category type, **Hotel**.             |     Daily room rate      |
|     Start date     |     The date when the expense item was first incurred.                                           |     09/13/2021           |
|     Daily Rate     |     The amount incurred for the expense item.                                                    |     200                  |
|     Quantity       |     The number of times the charge is repeated across a continuous period.                       |     3                    |

![Itemize expense.](https://user-images.githubusercontent.com/60446296/146428241-944b3824-91b1-43e9-8925-9e94bd49c952.png)

On saving the itemization , users will see an individual itemized line, for the quantity specified in their itemization grid, each starting on the date specified in the grid.

![Itemized report.](https://user-images.githubusercontent.com/60446296/146428356-e2e83e46-f9da-4505-bd84-33fa2b54116b.png)


