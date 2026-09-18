---
title: Time Entry Calendar interface (Preview)
description: This article explains how team members can interact with their time entries by using a new calendar interface.
author: mohitmenon
ms.date: 09/15/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time entry calendar interface overview (Preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE [preview note](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The time entry calendar interface gives users a new way to view and interact with their time entries. It introduces more intuitive ways of creating and editing time entries. In addition, users can show their time entries over various time horizons from **Daily**, **Weekly**, and **Monthly** views.

This article provides an overview of the interface and explains how to complete the following tasks:

- Enable the time entry calendar feature.
- View existing entries on the calendar.
- Create new time entries.
- Modify existing time entries.
- Submit, recall, and delete time entries.
- Switch time horizons from the calendar.
- Get visual snapshots and filter time entries.

## Enable the Time Entry Calendar

To enable the Time Entry Calendar, follow these steps:

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.141.0.X or later**. The Time Entry Calendar isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units appears. Double-tap or double-click the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Calendar (Preview) feature**, and then select **OK**. If the text **Disable Time Entry Calendar (Preview) feature** appears instead, the feature is already enabled.

After you enable the feature, a new menu item named **Calendar** appears in the **My Work** section of the Project Operations and Team Member apps.

## View existing entries on the calendar

To view time entries in the Time Entry Calendar interface, follow these steps:

1. Ensure that the Time Entry Calendar feature is enabled as described in the previous section.
1. In the **My Work** section, select **Calendar**. The Time Entry Calendar interface loads for the current work week.

Time entries appear as calendar entries. For each time entry, the project task name appears as the title. Below the project task name, you see the project name, then the duration, and then the entry status.

> [!TIP]
> For time entries that have a shorter duration, details such as the entry status, duration, or even the project name might be hidden. However, you can view all the details of any time entry by hovering over it to open a tooltip. To learn more, see [View external comments and descriptions from the calendar](#view-external-comments-and-descriptions-from-the-calendar).

The calendar entries are color-coded, based on the time entry status. By default, the following colors are used.

| Color | Status |
|---|---|
| Yellow | **Draft** or **Returned** |
| Blue | **Submitted** or **Recall Requested** |
| Green | **Approved** |

> [!NOTE]
> If the time entries that you're viewing on the calendar were originally created by using the standard time entry grid, and you didn't explicitly set a start time for them, Project Operations assigns a default start time of 12:00 AM (midnight). Therefore, you might need to scroll to the top of the calendar to view these entries.

### View external comments and descriptions from the calendar

If either the **External Comment** field or the **Description** field is set for a time entry, a dark blue triangle appears in the upper-right corner. To view the external comment or description, hover over the entry to open a tooltip. The tooltip shows all field values that are set for the time entry, including any external comment and description. The external comment or description is shown as the title of the tooltip.

:::image type="content" source="../media/tooltipdetails.png" alt-text="Screenshot that shows the tooltip for a time entry that an external comment and description were entered for. The tooltip also includes the project, project task, duration, role, and entry status for the entry.":::

## Create new time entries from the calendar

You can create time entries from the calendar in two ways:

- Use the **Create Time Entry** dialog (quick create dialog) to create a new time entry.
- Copy an existing time entry.

### Create a time entry by using the quick create dialog

Select any blank grid element on the calendar. Alternatively, select a blank section of the calendar and drag it until it has the duration you want. In both cases, a quick create dialog named **Create Time Entry** appears.

- In the **Start** field on the left side of the dialog, the start date and time are set based on the grid element that you selected. For example, if you select a blank grid element that starts at 1:00 PM on May 26, 2025, the **Start** field reflects those values (**5/26/2025 1:00 PM**).
- If you select an empty grid element, the **Duration** field is set to 30 minutes (**0h:30m**) by default. If you drag a section of the calendar to a specific duration (for example, three hours), the **Duration** field is set to that duration instead of 30 minutes.
- The **End** field reflects the start date and time plus the duration.

The other fields on the left side of the dialog are similar to the fields in the usual quick create dialog.

The new grid on the right side of the dialog shows projects where you're actively assigned to one or more project tasks. Use this grid to quickly fill in some of the fields on the left side of the dialog.

- When you expand the row for a project, a tree-like structure appears and shows the project tasks that are assigned to you.
- Below the row for a project task name, select the row for the task assignment (that is, the row that mentions the project resource name). The **Project**, **Project Task**, and **Role** fields on the left side of the dialog automatically populate based on the selected task assignment.

:::image type="content" source="../media/calendarqcformtasks.png" alt-text="Screenshot that shows the Create Time Entry dialog, where the Project, Project Task, and Role fields on the left side are populated based on a task assignment that is selected on the right side.":::

> [!NOTE]
> The **Create Time Entry** dialog shows only projects and tasks that have an active assignment on the date that you're logging time for. Therefore, you can use it to populate information only for those projects and tasks. If a task is already completed or hasn't yet started, you can't use the Time Entry Calendar to select any assignments for it. For these scenarios, switch to the standard time entry grid.

When you finish setting the fields, select **Save** to create the time entry.

### Add or remove fields from the quick create dialog

A form in Microsoft Power Apps called **Create Calendar Time Entry** supports the quick create dialog used within the Time Entry Calendar interface. 

To add or remove fields from this dialog, follow these steps:

1. Sign in to [Power Apps Maker Portal](https://make.powerapps.com) with admin credentials.
1. Use the picker in the upper-right corner to select the environment where you want to make changes to the dialog.
1. Go to **Tables**, and then select **Time Entry**.
1. Go to **Forms** and select _Create Calendar Time Entry_.
1. Add or remove fields from this form, and then select **Save and publish**.

   > [!NOTE]
   > When you add custom fields to this form, the calendar interface doesn't support _lookup_ fields. The calendar interface supports option-set and text fields.

### Create time entries using Outlook meetings

To use this feature, ensure that the [Use Outlook meetings as a time entry source](time-entry-configurations.md#use-outlook-meetings-as-a-time-entry-source) configuration is enabled.

To create a time entry using an Outlook meeting, follow these steps:

1. From the **My Work** section, select **Calendar**.
1. The Time Entry Calendar interface loads for the current work week.
1. A new **Show Meetings** toggle appears on the top ribbon. This toggle is off by default.
1. Switch the toggle **ON**. The calendar interface refreshes with all Outlook meetings in this week.
1. Double-click the meeting that you want to log time against. This step loads the calendar quick create form.
1. Select values for fields like _Project_, _Task_, and so on. Modify _Start_ or _End_ dates if needed. Select **Save**.
1. Follow the same steps to create time entries from other meetings.
1. Switch the **Show Meetings** toggle **OFF** after creating all such entries in the week.

  > [!NOTE]
  > The **Show Meetings** toggle persists only when you use the refresh icon within the calendar interface. Leaving the toggle **ON** when refreshing the calendar could lead to a slight delay in loading the calendar. The toggle doesn't persist when you leave the Time Entry Calendar and return (or refresh the browser tab). Currently, bulk creation of time entries from Outlook events isn't supported.

### Copy one or more existing entries

The Time Entry Calendar introduces a more intuitive process for copying time entry records. Follow these steps to copy one or more entries.

1. Select the time entry that you want to copy. To copy multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Use the standard <kbd>Ctrl</kbd>+<kbd>C</kbd> keyboard shortcut to copy the selected entries.

    > [!NOTE]
    > This shortcut is currently the only way to trigger a copy operation.

1. Identify the target date and time that you want to copy the entries to.
1. Select a grid element, or drag a blank section of the calendar to set the position where you want to paste the entries.
1. Use the standard <kbd>Ctrl</kbd>+<kbd>V</kbd> keyboard shortcut to paste the entries.

#### Information populated in copied entries

- **Time entry details** – The copy operation includes all the field values that are set in the visible time entry dialog (for example, **Project**, **Task**, **Role**, and **Description**).
- **Duration** – The duration of new entries depends on the target position that you select. If you select a single grid element in the calendar before you paste the copied entry, the **Duration** field is set to 30 minutes. If you select a blank section of the calendar and then drag it to a specific duration, the **Duration** field is set to that duration.

    > [!NOTE]
    > If you copy multiple entries and paste them in a target position, all the new entries have the same start and end dates and times (and the same duration).

## Modify time entries from the calendar

You can modify time entries from the calendar in the following ways:

- **Move an entry** – To move a calendar entry to a different position on the same date or a different date, select the entry, and then move it to the desired position on the calendar. The start and end dates and times are updated accordingly.
- **Resize an entry** – To resize a calendar entry, use the indicator at the top or bottom of the entry to increase or decrease its duration. The start and end dates and times are updated accordingly.
- **Edit fields by using a dialog** – Double-tap (or double-click) an editable entry to open a dialog named **Edit Time Entry**. This dialog resembles the **Create Time Entry** dialog. You can modify all fields for the time entry. When you finish, select **Save**.

    > [!NOTE]
    > Entries that have a status of **Submitted**, **Approved**, or **Recall Requested** are read-only. A lock symbol on these entries indicates that you can't edit them.

## Delete, submit, or recall time entries from the calendar

### Delete one or more time entries

To delete one or more time entries, follow these steps:

1. Select a time entry that has a status of **Draft** or **Returned**. To delete multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Select **Delete**.
1. In the message that appears, select **Delete** to confirm that you want to delete the records.

### Submit one or more time entries

To submit one or more time entries, follow these steps:

1. Select a time entry that has a status of **Draft** or **Returned**. To submit multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Select **Submit**. After a short time, the selected entries are submitted, the status is updated to **Submitted**, and the color is changed to blue on the calendar.

### Recall one or more time entries

To recall one or more time entries, follow these steps:

1. Select a time entry that has a status of **Submitted** or **Approved**. To recall multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Select **Recall**.
1. If any selected entry has a status of **Approved**, a dialog asks you to provide a reason for the recall. Enter a reason, and then select **Yes**.

## Switch time horizons on the calendar

By default, time entries are shown in a **Weekly** view. This experience is similar to the experience in the standard time entry grid. However, the Time Entry Calendar provides a view picker (dropdown menu) that you can use to switch between **Daily**, **Weekly**, **Monthly**, and **Agenda** views.

:::image type="content" source="../media/viewpicker.png" alt-text="Screenshot that shows the view picker expanded to show the different view options that are available for selection.":::

- **Weekly view** – This view is the default view. It shows all time entries for the current week. You can go to other weeks by using the calendar control or the **Next** (right arrow) and **Previous** (left arrow) buttons.

    > [!NOTE]
    > The **Weekly** view adheres to organization's settings for the start and end days of a week.

- **Agenda view** – This view shows a condensed version of the **Weekly** view. In this view, the title of each time entry is based on the value of the **Description** field. If no description is entered for an entry, the title is blank.
- **Daily view** – This view shows time entries for one day at a time. You can go to other days by using the calendar control or the **Next** (right arrow) and **Previous** (left arrow) buttons.
- **Monthly view** – This view shows all time entries for the calendar month. It includes a cell or grid element for each day of the month. You can go to other months by using the calendar control or the **Next** (right arrow) and **Previous** (left arrow) buttons.

    :::image type="content" source="../media/monthlyview.png" alt-text="Screenshot that shows an example of the Monthly view in the Time Entry Calendar interface.":::

## View target hours and filter time entries

### Get a visual snapshot of target hours

The Time Entry Calendar interface helps you track the number of hours that you should log by comparing your total hours with your target hours. Project Operations sets target hours based on the working hours that are configured for you.  

To view the visual snapshot, follow these steps:

1. Go to the Time Entry Calendar for the desired week.
1. Expand the **Charts** section.

    - The **Weekly Snapshot** section shows the total hours that you logged for the week and compares them with the target hours for that week.  
    - Next, a visualization provides a daily comparison between logged hours and target hours for each day of the week.
    - When you change the timeline, the snapshot updates to show a daily or monthly comparison.  

### Filter time entries by type or status

When you expand the **Charts** section, a **Legend for calendar entries** section appears at the bottom. In the legend, you can select or clear the selection of specific **Entry Status** or **Type** values to filter the time entries on the calendar.  

Applying a filter immediately updates which time entries are visible on the calendar. It also immediately updates the snapshot comparison.

## Declutter mode (preview only)

When you create time entries by using the standard time entry grid and don't set a start time, Project Operations assigns a default start time of 12:00 AM (midnight). This default can affect the visual experience when you view those time entries on the calendar, because multiple entries cluster together at 12:00 AM for each day. To help you view these time entries, the Time Entry Calendar introduces a *declutter mode*.

In declutter mode, the time entries no longer cluster at 12:00 AM. Instead, they show sequentially, starting at the beginning of your working hours. Declutter mode *temporarily* changes where the time entries *appear* on the calendar, so that they're easier to view. It doesn't actually change the start time of the entries.

To use declutter mode, follow these steps:

1. Go to the Time Entry Calendar for the desired week.
1. Confirm that one or more time entries that start at 12:00 AM are visible on the calendar.
1. Turn on the **De-clutter** option. (By default, the option is turned off.)

    The time entries for each day now appear sequentially, starting at the beginning of your working hours (8:00 AM in the following example).

    :::image type="content" source="../media/midnightentriesdecluttered.png" alt-text="Screenshot that highlights location of the De-clutter option and shows the result of turning it on for a user whose working hours begin at 8:00 AM.":::

### Declutter mode behavior

- **Which time entries are decluttered** – Declutter mode affects the display only of time entries that have a start time of 12:00 AM because you didn't explicitly set a start time for them. All existing time entries that you explicitly set a start time for remain as is. There's no change to their display or position on the calendar.
- **How the new position of time entries is determined** – Affected time entries show in new positions, based on the user's working hours. The entries are arranged sequentially, based on their **Created On** value. The entry that you created first appears at the beginning of the user's working day. The next entry immediately follows it.

    For example, a user has working hours from 8:00 AM to 5:00 PM. Two time entries must be decluttered. Each entry has a duration of two hours. Therefore, the entry that you created first shows from 8:00 AM to 10:00 AM, and the other entry shows from 10:00 AM to 12:00 PM.

### Making changes to decluttered entries

Declutter mode *temporarily* changes where time entries *appear* on the calendar, so that they're easier to view. It doesn't actually change the start time of the entries.

However, if you make and save any changes to a time entry while it's shown in its decluttered position, new start and end times that reflect that position are saved for the time entry record.

**Therefore, don't make changes to time entries while declutter mode is turned on.**

## Keyboard shortcuts 

These shortcuts apply only to the time entry calendar.

| Shortcut keys | Description |
|---------------|-------------|
| <kbd>C</kbd> | Open the **Create new event** pop-up editor using the current view's start date. |
| <kbd>T</kbd> | Go to today's time period. |
| <kbd>Alt</kbd>+<kbd>1</kbd>/<kbd>2</kbd>/<kbd>3</kbd>/<kbd>4</kbd>/<kbd>5</kbd> | Switch views. |
| <kbd>Shift</kbd>+<kbd>Right Arrow</kbd> | Go to the next time period. |
| <kbd>Shift</kbd>+<kbd>Left Arrow</kbd> | Go to the previous time period. |
| <kbd>Right Arrow</kbd> or <kbd>Down Arrow</kbd> | Move focus to the next event. |
| <kbd>Left Arrow</kbd> or <kbd>Up Arrow</kbd> | Move focus to the previous event. |
| <kbd>Enter</kbd> | Open the **Edit** window for the selected event. |
| <kbd>Esc</kbd> | Close the **Edit** pop-up window. |
| <kbd>Delete</kbd> or <kbd>Backspace</kbd> | Open the **Delete** confirmation pop-up to remove the time entry. |
| <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>O</kbd> | Open the time entry in a new tab. |
| <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd> | Submit the time entry. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
