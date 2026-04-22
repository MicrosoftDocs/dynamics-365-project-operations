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

The Modern Time Entry Grid reduces the reliance on forms by providing in-grid editing for primary time entry fields like Project, Task, Role, Subcontract and Subcontract Line. In addition, users can Show or Hide columns visually without losing information from those fields when creating in-line time entries across the week.

This article contains the following sections:
- Switch to the Modern Time Entry Grid.
- Editing time entry fields directly from the grid. 
- Show or Hide columns from the grid without losing information.

## Switch to the Modern Time Entry Grid

To use the modern grid, follow these steps:

1. Sign in to Project Operations or Project Operations Team Member and navigate to **Time Entries** under **My Work**.
1. Select **Show As** from the ribbon at the top of the page. Pick **Modern Time Entry Grid** from the options listed.

## Editing time entry fields directly from the grid

On the standard Time Entry Grid (not modern), Modifications to fields other than Duration required the use of the **Edit Row** or **Edit Entry** form. The Modern Grid allows users to make such modifications directly from the grid, without using a form (restricted to _Project, Project Task, Role, Subcontract & Subcontract Line_ fields). 

In-line editing follows these rules in the modern grid:
- Project Task can only be selected from the grid when Project is already populated.
- The list of Project Tasks will be filtered based on the selected Project.
- Clearing Project field in-line also clears the Project Task (if any) that was populated.
- Subcontract field is filtered based on Project, Task and selected Role. This behaviour is similar to the logic used within the Quick Create form for time entry. Similarly for Subcontract lines, with an added filter for Subcontract.
- Clearing Subcontract also clears the previously selected Subcontract Line.

> [!NOTE]
> Bulk Editing (multiple rows) is not supported on the Modern Grid.

## Show and Hide columns from the grid without losing information

This capability is currently available as a **preview feature in early access**. Enable this feature by following these steps:

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.166.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Enhancement on the Modern Time Entry grid feature**, and then select **OK**. If the text **Disable Enhancement on the Modern Time Entry grid feature** is shown instead, the feature is already enabled.

To use the feature:
1. Switch to the **Modern Time Entry Grid**. A new ribbon button named **Show/Hide** is visible.
2. The list of columns displayed within the **Show/Hide** drop-down come from the Time Entry View that is currently selected (Default view being _My Weekly Time Entries_). In addition to this, any columns added via **Edit Columns** is also included in this drop-down (until the page is refreshed).
3. Hiding one or more columns visually hides them from the grid, to make the Time Entry view less cluttered and more readable.
4. When creating in-line entries for a row - values populated for any hidden columns will still be maintained on the newly created time entries as well (no loss of information).
5. Values for newly created entries can be verified by un-hiding (showing) those columns once again.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
