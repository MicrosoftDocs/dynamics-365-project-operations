---
title: Time Entry Calendar interface (preview)
description: This article explains how team members can interact with their time entries using a new calendar interface.
author: mohitmenon
ms.date: 06/03/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time Entry Calendar interface overview (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

The Time Entry Calendar interface provides users with a new way to view and interact with their time entries. This interface introduces more intuitive ways of creating and editing time entries. In addition, users also get to display their time entries over various time horizons from Daily, Weekly, and Monthly views.

This overview consists of the following sections:

- Enabling the Time Entry Calendar feature
- View existing entries on the calendar
- Create new time entries
- Modify existing time entries
- Submit, Recall, or Delete time entries
- Switch time horizons from the calendar
- Get visual snapshots and filter time entries


## Enable the Time Entry Calendar 

To enable Time Entry Calendar, follow these steps.

1. Ensure your Project Operations environment is updated to version **4.141.0.X or higher**, since the Time Entry Calendar isn't available on earlier versions.
1. Sign in to Dynamics 365 Project Operations as a System Administrator.
1. On the left navigation, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Calendar (Preview) feature**, and then select **OK**.
1. If instead you see the text **Disable Time Entry Calendar (Preview) feature**, it implies that the feature is already enabled.

Once this feature is enabled, a new menu item named **Calendar** is visible under the **My Work** section of the Project Operations and Team Member apps.

## View existing entries on the calendar

To view time entries using the calendar interface, follow these steps.

1. Ensure the **Time Entry Calendar feature** is enabled as per the previous section.
1. Under the **My Work** section, select **Calendar**.
1. The Time Entry Calendar loads for the current work week.
1. Time entries are visible as calendar entries, with the title of each entry as the **Project Task** name and **Project** name right below it along with **Duration**.

   > [!NOTE]
   > Details like Duration, Entry Status, or even Project Name **may be hidden** for time entries with shorter durations, but can be viewed by using the tool-tip mentioned later in this article.

1. The calendar entries are color coded based on time entry status with the default colors as:
   - **Yellow:** _Draft_ and _Returned_
   - **Blue:** _Submitted_ and _Recall Requested_
   - **Green:** _Approved_

   > [!NOTE]
   > While viewing time entries on the calendar that were originally created using the Time Entry Grid, users may have to **scroll to the top** since Project Operations sets **default start time as midnight (12 am)** when no start time is explicitly mentioned. 

### View external comments from the calendar

- Time entries with either the **External Comment** or **Description** populated have a blue icon (similar to the time entry grid) to indicate this on the top-right of the entry.
- To view the comment or description, hover the cursor over an entry. Doing so, brings up a **tool-tip section** _(see image)_ that covers all populated fields for that time entry. 
   - If an **External Comment** or **Description** is entered, then they show up as the title of this section.

   :::image type="content" source="../media/tooltipdetails.png" alt-text="Screenshot that shows a tooltip to view external comments and other time entry fields.":::

## Create new time entries from the calendar

Time entries can be created from the calendar in two ways:

- Creating a time entry using the **New Time Entry form** (quick create form) OR
- By copying an existing time entry

### Creating a time entry using quick create form

- Select any grid element on the calendar that is empty. This step opens a pop-up form titled **Create New Entry**.
- The **Date** and **Start Time** are set depending on which grid element was selected.
   - _For example, if a user selects the blank grid element that starts at 1 pm on May 26 then Date and Start Time are defaulted with these values._
- By default, **Duration** is set to **30 minutes** when the user just selects any of the empty grid elements. 
   - To set a different Duration, the user can alternatively **click + drag** an empty section of the calendar to a desired duration _(For example, 3 hours)_ and the Duration field defaults with that value instead of just 30 minutes.
- On the left side of this form, you find a list of fields similar to the usual Quick Create form.

A **new section** is visible on the right side of this form, where users can see a list of Projects that they're actively assigned to on one or more Project Tasks.

- When you expand any of the Projects, a tree-like structure appears that highlights the assigned Project Tasks for this user.
- Select the row below the Project Task name that mentions the Resource's name. Doing this selection, populates **Project**, **Project Task**, and **Role** fields based on the task assignment that was selected _(see image for an example of this)._

  :::image type="content" source="../media/calendarqcformtasks.png" alt-text="Screenshot that shows how Project, Task and Role fields get populated by selecting a task assignment.":::
- Select **Save** after populating all the necessary fields, to finally create the time entry.

   > [!NOTE]
   > Only Projects and Tasks that have an **active assignment on the Date for which time is being logged**, are visible and can be populated using the Create New Entry form. 
   > This implies that any assignments on a **task that has already completed or is yet to begin**, **can not be selected** using the Time Entry Calendar. For such scenarios, **switch to** the standard **Time Entry Grid**.


### Copying one or more existing entries

The Time Entry Calendar also introduces more **intuitive copying** of time entry records. Follow these steps to copy one or more entries:
- Select the time entry that needs to be copied.
- Use the standard **Ctrl + C** shortcut to copy the entry _(this shortcut is currently the only way to trigger a copy)_.
- Identify the target date and time where this entry is to be copied.
- Select a grid element or **click + drag** an empty section of the calendar to set that that as the position where you'd like to paste the entry.
- Use the standard **Ctrl + V** shortcut to paste the entry.
- Copying can also be done by selecting more than one time entry using **Ctrl + click** as mentioned in early sections.

#### Fields populated for copied entries
- **Time Entry Details:** Copying a time entry copies all the fields that are populated on the visible time entry form _(Project, Task, Role, Description, etc.)_.
- **Duration** for the pasted entries is decided based on the target position that was identified. This is set to either **30 minutes** if a single calendar element was selected, or a **larger duration** if an empty section of the calendar was selected using **click + drag** before pasting the entries.

   > [!NOTE]
   > If multiple entries are copied and pasted at a target position, all of the new entries share the same Start and End times (and Duration). 

## Modify time entries from the calendar

Time entries can be modified from the calendar in two ways:

- **Moving or Resizing an entry**: 
   - Calendar entries can be **moved from one position to another** _(including a different date) _by selecting and moving the entry to the desired area on the calendar. This updates the **Start, End Times**, or **Date** field (if moved to a different day), depending on how the entry is repositioned.
   - Similarly, calendar entries can be **resized** by using the indicators at the top or bottom of an entry to **increase or decrease their Duration**.
- **Editing fields using a form**:
   - Double clicking an editable entry opens a similar pop-up form titles **Edit Time Entry**.
   - All fields corresponding to the time entry can be modified, before selecting **Save**.
  
   > [!NOTE]
   > All read-only entries _(Submitted, Approved, Recall Requested)_ have a visible **lock icon** to indicate this property. Only entries without this icon can be edited in the ways mentioned here.

## Submit, Recall, or Delete time entries from the calendar

### Delete one or more time entries

To delete one or more time entries, follow these steps.

1. Select _(single click)_ a Draft or Returned time entry. To select **multiple entries**, use **Ctrl + Click** to continue selecting other entries as well.
1. Select **Delete** buttons from the top ribbon.
1. Confirmation is required before deleting records.
1. Select **Delete** from the pop-up.


### Submit one or more time entries

To submit one or more time entries, follow these steps.

1. Select _(single click)_ a Draft or Returned time entry. To select **multiple entries**, use **Ctrl + Click** to continue selecting other entries as well.
1. Select **Submit** buttons from the top ribbon. In a few moments, the selected entry or entries are submitted and the color changes to Blue.

### Recall one or more time entries

To recall one or more time entries, follow these steps.

1. Select _(single click)_ a Submitted or Approved time entry. To select **multiple entries**, use **Ctrl + Click** to continue selecting other entries as well.
1. Select **Recall** buttons from the top ribbon. If one of the selected entries was in **Approved** state, a pop-up asking for a reason for recall is displayed. Enter the reason and Select **Yes**.
 
## Switch time horizons on the calendar

By default, time entries are displayed in a **Weekly** view, similar to the time entry grid experience. However, the Time Entry Calendar comes with the ability to switch between Daily, Weekly, Monthly and an "Agenda" view by using the **View picker** (drop-down). 

:::image type="content" source="../media/viewpicker.png" alt-text="Screenshot that shows the view picker to switch time horizons.":::

- **Weekly View**: Default view that displays all time entries for the current week and lets users navigate to other weeks using the calendar control or next, previous buttons.

   > [!NOTE]
   > The Weekly view also adheres to organization settings for Start and End days of a week.
   
- **Agenda View**: This view displays a condensed version of the weekly view, with a title given to each time entry based on the **Description** field. If no description is entered for an entry, then the title is blank.
- **Daily View**: This view displays time entries one day at a time and users can switch to next and previous days or pick a specific day via the calendar control.
- **Monthly View**: This view displays all time entries across the calendar month, with a cell or grid element visible for each day of the month.

:::image type="content" source="../media/monthlyview.png" alt-text="Screenshot that shows the monthly view of the calendar interface.":::


## View target hours and filter time entries

### Get a visual snapshot of target hours

The Time Entry Calendar interface also provides users with the ability to track how many hours they're supposed to log by comparing their total hours with "Target" hours, based on their working hours configured in Project Operations. 

To view the visual snapshot, follow these steps.

1. Navigate to the **Time Entry Calendar** for the desired week.
1. Expand the collapsed **Charts** section.
1. First, a **Weekly Snapshot** provides the total hours logged for the week and compares it with the Target for that week.
1. Next, a visualization provides a daily comparison between hours logged and the target hours for each day.
1. This snapshot updates to show **Daily** and **Monthly** comparisons as well, when the user changes the timeline.

### Filter time entries by type or status

To filter time entries by type or status, follow these steps.

1. With the Charts section open, a **Legend for calendar entries** is displayed at the bottom.
1. This section allows users **select or hide** the **Entry Status** for which they want to filter time entries.
1. Doing so immediately updates which time entries are visible on the calendar and updates the snapshot comparison immediately as well.
1. Similarly, users can **check or uncheck** the **Type** of time entries they want to filter by. The calendar and snapshot get updated immediately. 

## Declutter mode (Preview only)

Entries created using the standard Time Entry Grid experience without an explicit **Start time**, are defaulted to midnight (12 am) as their starting time. When such entries are viewed on the Time Entry Calendar, the visual experience can be impacted since **multiple time entries are cluttered together** at the start of the day (at 12 am). To make it easier to view existing time entries, use **Declutter mode**. 

To use **Declutter mode**, follow these steps.

1. Navigate to the Time Entry Calendar for the desired week.
1. Confirm that one or more time entries that start at 12 am are visible on the calendar (see image for an example).
1. By default, the **Declutter** **toggle** is disabled or set to **OFF**.
1. Enable **Declutter** mode by switching **ON** the toggle _(see image for an illustration of this mode)_.

   :::image type="content" source="../media/midnightentriesdecluttered.png" alt-text="Screenshot that shows decluttered display.":::

### **Declutter mode behavior**

- **Which time entries get decluttered:** This mode only declutters or temporarily moves entries that **did not have an explicit Start Time** populated for them (all entries with Start Time as 12 am are decluttered here).
- **How the new position of time entries is set:** The identified time entries are temporarily moved based on the user's working hours. Entries created first (based on **Created On** date) are stacked at the Start of the day, with the next entry immediately following the previous entry and so on.
   - **For example:** _A user has working hours from 8 am to 5 pm. There are two time entries of two hours each that need to be decluttered. The entry that was created first gets displayed from 8 am to 10 am, followed by the next entry from 10 am to 12 pm._
- **Existing entries with Start Time populated:** All existing time entries that had an explicit Start time populated are kept as is, so there isn't a change in their display or position on the calendar. 

### Making changes to decluttered entries

- The "Declutter" mode is only a **temporary** change in how the entries are displayed, to make it easier to view such entries.
- However, if a user makes **any modifications** to time entries while they're in decluttered mode then the **new Start and End times are also saved** for those time entry records.

> [!IMPORTANT]
> The Declutter mode is only a **temporary** change in how the entries are displayed, to make it easier to view such entries. Don't make changes to time entries in this mode because doing so modifies their Start and End times as mentioned in the previous section.


[!INCLUDE[footer-include](../includes/footer-banner.md)]




