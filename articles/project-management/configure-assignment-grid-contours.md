---
title: Assignments grid configuration
description: Learn about configurable time scale and granularity options on the assignments grid in Dynamics 365 Project Operations.
author: dishantpopli
ms.author: dishantpopli
ms.date: 05/09/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Assignments grid configuration overview

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The assignments grid in Dynamics 365 Project Operations displays resource assignment contours across time periods. Project managers can view 7, 14, or 21 time periods on the assignments grid, and administrators can configure the default time scale and time granularity for their organization. These defaults apply organization-wide and determine the initial view when project managers open the assignments grid on any project.


## Configure the default time scale and granularity

1. Go to **Settings** > **Parameters**.
2. Locate the **Assignments view** section.
3. In the **Time Scale** field, select the default number of visible time period columns:
   - **7**—Displays 7 columns
   - **14**—Displays 14 columns (default)
   - **21**—Displays 21 columns
4. In the **Time Granularity** field, select the default granularity for each column:
   - **Days** (default)
   - **Weeks**
   - **Months**
   - **Years**
5. Select **Save**.

## Change the time scale

The time scale controls how many time period columns appear on the grid. You can choose 7, 14, or 21 columns.

1. Go to **Projects** and open the project you want to view.
2. Select the **Tasks** tab, then select the **Assignments** view.
3. On the toolbar of the assignments grid, locate the **Time Scale** dropdown.
4. Select the desired value: **7**, **14**, or **21**.

   The grid refreshes to display the selected number of time period columns.

   > [!NOTE]
   > When you select 14 or 21, the grid displays more columns horizontally and may need scrolling.

## Change the time granularity

The time granularity controls the duration that each column represents.

1. On the toolbar of the assignments grid, locate the **Time Granularity** dropdown.
2. Select the desired value: **Days**, **Weeks**, **Months**, or **Years**.

   The grid refreshes to display assignment contours at the selected granularity.

> [!IMPORTANT]
> Changes to time scale and time granularity are temporary. When you reopen the project or switch tabs or refresh your session, these values revert to the defaults configured by your administrator in project parameters.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
