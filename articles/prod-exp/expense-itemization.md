---
title: Expense itemization
description: This article explains how to itemize expenses using the reimagined Expense workspace.
author: mukumarm
ms.author: mukumarm
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense itemization

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

Organizations often require employees to provide a detailed breakdown of expenses incurred during travel. For example, a hotel folio might contain several itemized lines for room rate, tax, parking, and other miscellaneous expenses incurred each day during the duration of stay. Or a meal expense might require that you provide a more granular breakdown for breakfast, lunch, or dinner. Whatever the needs of the organization, each expense category can reflect the subcategories or the line items that make up an expense. While **Expense management** always supported itemization, the **Reimagined expense** workspace enables more efficient itemization when the feature **Ability to itemize recurring expenses quickly** is enabled.  

## Enable quick itemization 

Use the **Ability to itemize recurring expenses quickly** feature to itemize recurring expenses quickly while avoiding the need to enter the daily expenses each time for the duration of stay. Complete the following steps to enable quick itemization.

1. Go to the **Feature Management** workspace and in the list of features, locate and select, **Expense Reports Reimagined**. 
1. Select **Enable now**. 
1. In the feature list, locate and select, **Ability to itemize recurring expenses quickly**.
1. Select **Enable now**.  

## Itemization grid 

You can itemize an expense category when it has subcategories or different components that make up that expense. 
To itemize an expense, select the expense line in the expense report. In the **Expense details** pane, select **Actions** > **Itemize**. The **Itemization** slider reveals a grid with fields. The following table provides an example of each field in the grid and how the field is rendered in the expense report. 

|     Field          |     Description                                                                                  |     Example              |
|--------------------|--------------------------------------------------------------------------------------------------|--------------------------|
|     Subcategory    |     The list of subcategories configured under the expense category type, **Hotel**.             |     Daily room rate      |
|     Start date     |     The date when the expense item was first incurred.                                           |     09/13/2021           |
|     Daily Rate     |     The amount incurred for the expense item.                                                    |     200                  |
|     Quantity       |     The number of times the charge is repeated across a continuous period.                       |     3                    |

:::image type="content" source="media/Itemization%20screen%201.png" alt-text="Screenshot of the Itemization grid with fields for subcategory, start date, daily rate, and quantity.":::

When you save an itemization, you see an individual itemized line for the quantity specified in the Itemization grid. Each line starts on the date that you specify in the grid.

:::image type="content" source="media/Itemization%20screen%202.png" alt-text="Screenshot of an itemized expense report showing individual itemized lines for each day.":::

