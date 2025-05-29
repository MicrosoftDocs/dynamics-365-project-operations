---
title: New Time Entry Calendar interface (Preview)
description: This article explains how team members can use interact with their time entries using a new, calendar interface.
author: mohitmenon
ms.date: 05/29/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Overview of the Time Entry Calendar (Preview) interface

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The Time Entry Calendar interface provides users with a new way to view and interact with their time entries. This interface introduces more intuitive ways of creating and editing time entries. In addition, users also get to display their time entries over various time horizons from Daily, Weekly and Monthly views.

This overview consists of the following sections
- Enabling the Time Entry Calendar feature
- View existing entries on the calendar
- Create new time entries
- Modify existing time entries
- Submit, Recall or Delete time entries
- Get snapshots and filter time entries


## Enable the Time Entry Calendar 
To enable Time Entry Calendar, follow these steps.

1. Ensure your Project Operations environment is running version 4.141.0.X or higher, since the Time Entry Calendar is not available or earlier versions.
1. Sign in to Dynamics 365 Project Operations as a System Administrator.
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Calendar (Preview) feature**, and then select **OK**.
1. If instead you see the text **Disable Time Entry Calendar (Preview) feature**, it implies that the feature is already enabled.

Once this feature is enabled, a new menu item named **Calendar** will be visible under the **My Work** section of the Project Operations and Team Member apps.

:::image type="content" source="../media/1calendarmenuitem.png" alt-text="Screenshot that shows the new Calendar menu item.":::

## View existing entries on the calendar

To view time entries using the calendar interface, follow these steps:
1. Ensure the **Time Entry Calendar feature** is enabled as per the previous section.
2. Under the **My Work** section, select **Calendar**.
3. The Time Entry Calendar will load for the current work week.
4. Time entries will be visible as calendar entries, with the title of each entry as the **Project Task** name and **Project** name right below it along with **Duration**.
> [!NOTE]
> Details like Duration, Entry Status or even Project Name may get hidden for shorter duration time entries but can be viewed by using the tool-tip mentioned above.

5. The calendar entries are colour coded based on time entry status with the default colors as shown below:

| Status     	| Colour               	|
|------------	|------------------------	|
| Draft, Returned 	| Yellow	|
| Submitted, Recall Requested | Blue  |
| Approved 	| Green	|

:::image type="content" source="../media/2viewentries.png" alt-text="Screenshot that shows some sample time entrie when viewed using the calendar interface.":::


### Viewing time entry details

Viewing the populated fields for each time entry can be done in two ways:
1. Double clicking a time entry will open a pop-up form, that can be used to view or modify entries.
2. Hovering the cursor over a time entry brings a tool-tip section that covers the populated fields for that time entry. If an **External Comment** or **Description** is entered then they will show up as the title of this section. 
 

> [!NOTE]
> While viewing time entries on the calendar that were originally created using the Time Entry Grid, users may have to scroll up to the top since Project Operations sets default start time as midnight (12 am) when no start time is explicitly mentioned. 


## Create new time entries from the calendar

## Modify time entries from the calendar

## Submit, Recall or Delete time entries from the calendar

## View a snapshot and filter time entries




