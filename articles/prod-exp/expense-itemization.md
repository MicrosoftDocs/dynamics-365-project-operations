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

Organizations often require employees to provide the detailed breakdown of expenses incurred during travel.  For e.g. a hotel folio may contain several itemized lines for room rate, tax , parking, and other miscellaneous expenses incurred each day during the duration of stay . Or a Meal expense may require providing more granular expense breakdown for breakfast, lunch or dinner. Whatever the needs of the Organization, each expense category can be set up to reflect the subcategories or the line items making up that expense. While itemization has always been supported in D365 expense management module, the Reimagined expense workspace enables more efficient itemization when the "Ability to itemize recurring expenses quickly" feature is turned on.  

## Enabling Quick Itemization 

Navigate to Feature Management and first enable the "Expense Reports Reimagined" feature and then turn on the "Ability to itemize recurring expenses quickly " feature. 

The "Ability to itemize recurring expenses quickly " feature enables users to itemize recurring expenses quickly while avoiding the need to enter the daily expenses each time for the duration of stay.


## Itemization Grid 

If an Expense category has subcategories, then these expenses can be itemized.  To Itemize an expense, select the expense line in the expense report, and in the expense details pane, click on "Actions"--> "Itemize". The Itemization slider will reveal a grid with the following fields. Below is an example of each field in the grid and how this will render in the expense report. 

|     Field Name     |     Field   Description                                                                          |     Example(s)           |
|--------------------|--------------------------------------------------------------------------------------------------|--------------------------|
|     Subcategory    |     This is the list of subcategories configured under the expense category of type = Hotel.     |     Daily room   rate    |
|     Start date     |     This is the first date when the expense item was incurred.                                   |     09/13/2021           |
|     Daily Rate     |     This is the amount incurred for that expense item.                                           |     200                  |
|     Quantity       |     This is the number of times the charge is repeated/recurring across a continuous period.     |     3                    |

![image](https://user-images.githubusercontent.com/60446296/146428241-944b3824-91b1-43e9-8925-9e94bd49c952.png)

On saving the itemization , users will see an individual itemized line, for the quantity specified in their itemization grid, each starting on the date specified in the grid.

![image](https://user-images.githubusercontent.com/60446296/146428356-e2e83e46-f9da-4505-bd84-33fa2b54116b.png)


