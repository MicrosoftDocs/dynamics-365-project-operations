---
title: Modern Time Entry Grid
description: Learn about the improvements provided by Modern Time Entry Grid for Microsoft Dynamics 365 Project Operations users.
author: mohitmenon
ms.date: 04/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Modern Time Entry Grid

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Modern Time Entry Grid reduces the reliance on forms by providing in-grid editing for primary time entry fields like Project, Task, Role, Subcontract, and Subcontract Line. You can also show or hide columns visually without losing information from those fields when you create in-line time entries across the week.

This article contains the following sections:

- Switch to the Modern Time Entry Grid.
- Edit time entry fields directly from the grid.
- Show or hide columns from the grid without losing information.

## Switch to the Modern Time Entry Grid

To use the modern grid, follow these steps:

1. Sign in to Dynamics 365 Project Operations or Project Operations Team Member and go to **Time Entries** under **My Work**.
1. Select **Show As** from the ribbon at the top of the page. Select **Modern Time Entry Grid** from the options listed.

## Edit time entry fields directly from the grid

On the standard Time Entry Grid (not modern), you need to use the **Edit Row** or **Edit Entry** form to change fields other than Duration. The modern grid lets you make these changes directly from the grid, without using a form. This direct editing is restricted to the _Project, Project Task, Role, Subcontract, and Subcontract Line_ fields.

In-line editing follows these rules in the modern grid:

- You can select the Project Task from the grid only when the Project is already populated.
- The list of Project Tasks is filtered based on the selected Project.
- Clearing the Project field in-line also clears the Project Task (if any) that you populated.
- The Subcontract field is filtered based on Project, Task, and selected Role. This behavior is similar to the logic used within the Quick Create form for time entry. Similarly for Subcontract lines, with an added filter for Subcontract.
- Clearing **Subcontract** also clears the previously selected subcontract line.

> [!NOTE]
> The modern grid doesn't support bulk editing (multiple rows).

## Show and hide columns from the grid without losing information

This capability is currently available as a **preview feature in early access**. Enable this feature by following these steps:

To enable the **Enable Enhancement on the Modern Time Entry grid** feature, follow these steps:

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.166.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units appears. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Enhancement on the Modern Time Entry grid feature**, and then select **OK**. If the text **Disable Enhancement on the Modern Time Entry grid feature** appears instead, the feature is already enabled.

To show and hide columns from the grid, follow these steps:

1. Switch to the **Modern Time Entry Grid**. A new ribbon button named **Show/Hide** is visible.
1. The list of columns displayed within the **Show/Hide** drop-down comes from the Time Entry view that is currently selected (default view is _My Weekly Time Entries_). In addition to these fields, the drop-down also includes any columns you add through **Edit Columns** (until the page is refreshed).
1. To make the Time Entry view less cluttered and more readable, hide one or more columns to visually hide them from the grid.
1. When you create in-line entries for a row, the values you enter for any hidden columns are maintained on the newly created time entries (no loss of information).
1. You can verify values for newly created entries by unhiding (showing) those columns.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
