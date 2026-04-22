---
title: Modern Time Entry Grid
description: This article covers the improvements provided by Modern Time Entry Grid for Project Operations users.
author: mohitmenon
ms.date: 04/20/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Modern Time Entry Grid

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Modern Time Entry Grid reduces the reliance on forms by providing in-grid editing for primary time entry fields like Project, Task, Role, Subcontract and Subcontract Line. In addition, this grid provides the ability to Show or Hide columns visually without losing information from those fields when creating in-line time entries across the week.

This article contains the following sections:
- Switch to the Modern Time Entry Grid.
- Editing time entry fields directly from the grid. 
- Show or Hide columns from the grid without losing information.

## Switch to the Modern Time Entry Grid

To use the modern grid, follow these steps:

1. Sign in to Project Operations or Project Operations Team Member and navigate to **Time Entries** under **My Work**.
1. Select **Show As** from the ribbon at the top of the page. Pick **Modern Time Entry Grid** from the options listed.

## Editing time entry fields directly from the grid

Prior to the modern grid, Modifications to fields other than Duration required the use of the **Edit Row** or **Edit Entry** form. The Modern Grid allows users to make such modifications directly from the grid, without using a form (restricted to _Project, Project Task, Role, Subcontract & Subcontract Line_ fields). 

In-line editing follows these rules in the modern grid:
- Project Task can only be selected from the grid when Project is already populated.
- The list of Project Tasks will be filtered based on the selected Project.
- Clearing Project field in-line will also clear the Project Task (if any) that was populated.
- Subcontract field is filtered based on Project, Task and Role selected (similar to the logic used within the Quick Create form for time entry). Similarly for Subcontract lines, with the added filter of Subcontract.
- Clearing Subcontract will also clear the previously selected Subcontract Line.

> [!NOTE]
> Bulk Editing (multiple rows) is not supported on the Modern Grid.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
