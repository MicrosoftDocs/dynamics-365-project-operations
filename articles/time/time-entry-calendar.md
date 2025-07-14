---
title: Time Entry Calendar interface (preview)
description: This article explains how team members can interact with their time entries by using a new calendar interface.
author: mohitmenon
ms.date: 06/03/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time Entry Calendar interface overview (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Time Entry Calendar interface gives users a new way to view and interact with their time entries. It introduces more intuitive ways of creating and editing time entries. In addition, users can show their time entries over various time horizons from **Daily**, **Weekly**, and **Monthly** views.

This article provides an overview of the interface and explains how to complete the following tasks:

- Enable the Time Entry Calendar feature.
- View existing entries on the calendar.
- Create new time entries.
- Modify existing time entries.
- Submit, recall, and delete time entries.
- Switch time horizons from the calendar.
- Get visual snapshots and filter time entries.

## Enable the Time Entry Calendar

To enable the Time Entry Calendar, follow these steps.

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.141.0.X or later**. The Time Entry Calendar isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Calendar (Preview) feature**, and then select **OK**. If the text **Disable Time Entry Calendar (Preview) feature** is shown instead, the feature is already enabled.

After the feature is enabled, a new menu item that is named **Calendar** appears in the **My Work** section of the Project Operations and Team Member apps.

## View existing entries on the calendar

To view time entries in the Time Entry Calendar interface, follow these steps.

1. Ensure that the Time Entry Calendar feature is enabled as described in the previous section.
1. In the **My Work** section, select **Calendar**. The Time Entry Calendar interface is loaded for the current work week.

Time entries appear as calendar entries. For each time entry, the project task name is shown as the title. Below the project task name appear the project name, then the duration, and then the entry status.

> [!TIP]
> For time entries that have a shorter duration, details such as the entry status, duration, or even the project name might be hidden. However, you can view all the details of any time entry by hovering over it to open a tooltip. Learn more in the [View external comments and descriptions from the calendar](#view-external-comments-and-descriptions-from-the-calendar) section.

The calendar entries are color-coded, based on the time entry status. By default, the following colors are used.

| Color | Status |
|---|---|
| Yellow | **Draft** or **Returned** |
| Blue | **Submitted** or **Recall Requested** |
| Green | **Approved** |

> [!NOTE]
> If the time entries that you're viewing on the calendar were originally created by using the standard time entry grid, and no start time was explicitly set for them, Project Operations assigns a default start time of 12:00 AM (midnight). Therefore, you might have to scroll to the top of the calendar to view these entries.

### View external comments and descriptions from the calendar

If either the **External Comment** field or the **Description** field is set for a time entry, a dark blue triangle appears in the upper-right corner. To view the external comment or description, hover over the entry to open a tooltip. The tooltip shows all field values that are set for the time entry, including any external comment and description. The external comment or description is shown as the title of the tooltip.

:::image type="content" source="../media/tooltipdetails.png" alt-text="Screenshot that shows the tooltip for a time entry that an external comment and description were entered for. The tooltip also includes the project, project task, duration, role, and entry status for the entry.":::

## Create new time entries from the calendar

Time entries can be created from the calendar in two ways:

- Create a brand-new time entry by using the **Create Time Entry** dialog (quick create dialog).
- Copy an existing time entry.

### Create a time entry by using the quick create dialog

Select any blank grid element on the calendar. Alternatively, you can select a blank section of the calendar and drag it until it has the required duration. In both cases, a quick create dialog that is named **Create Time Entry** appears.

- In the **Start** field on the left side of the dialog, the start date and time are set based on the grid element that you selected. For example, if you selected a blank grid element that starts at 1:00 PM on May 26, 2025, the **Start** field reflects those values (**5/26/2025 1:00 PM**).
- If you selected an empty grid element, the **Duration** field is set to 30 minutes (**0h:30m**) by default. If you dragged a section of the calendar to a specific duration (for example, three hours), the **Duration** field is set to that duration instead of 30 minutes.
- The **End** field reflects the start date and time plus the duration.

The other fields on the left side of the dialog are similar to the fields in the usual quick create dialog.

The new grid on the right side of the dialog shows projects where you're actively assigned to one or more project tasks. You can use this grid to quickly fill in some of the fields on the left side of the dialog.

- When you expand the row for a project, a tree-like structure appears and shows the project tasks that are assigned to you.
- Below the row for a project task name, select the row for the task assignment (that is, the row that mentions the project resource name). Notice that the **Project**, **Project Task**, and **Role** fields on the left side of the dialog are automatically populated based on the selected task assignment.

:::image type="content" source="../media/calendarqcformtasks.png" alt-text="Screenshot that shows the Create Time Entry dialog, where the Project, Project Task, and Role fields on the left side are populated based on a task assignment that is selected on the right side.":::

> [!NOTE]
> The **Create Time Entry** dialog shows only projects and tasks that have an active assignment on the date that time is being logged for. Therefore, it can be used to populate information only for those projects and tasks. If a task has already been completed or hasn't yet been started, you can't use the Time Entry Calendar to select any assignments for it. For these scenarios, switch to the standard time entry grid.

When you finish setting the fields as required, select **Save** to create the time entry.

### Copy one or more existing entries

The Time Entry Calendar introduces a more intuitive process for copying time entry records. Follow these steps to copy one or more entries.

1. Select the time entry that must be copied. To copy multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Use the standard <kbd>Ctrl</kbd>+<kbd>C</kbd> keyboard shortcut to copy the selected entries.

    > [!NOTE]
    > This shortcut is currently the only way to trigger a copy operation.

1. Identify the target date and time that the entries must be copied to.
1. Select a grid element, or drag a blank section of the calendar to set the position where you want to paste the entries.
1. Use the standard <kbd>Ctrl</kbd>+<kbd>V</kbd> keyboard shortcut to paste the entries.

#### Information populated in copied entries

- **Time entry details** – All the field values that are set in the visible time entry dialog are copied (for example, **Project**, **Task**, **Role**, and **Description**).
- **Duration** – The duration of new entries depends on the target position that is selected. If you select a single grid element in the calendar before you paste the copied entry, the **Duration** field is set to 30 minutes. If you select a blank section of the calendar and then drag it to a specific duration, the **Duration** field is set to that duration.

    > [!NOTE]
    > If you copy multiple entries and paste them in a target position, all the new entries have the same start and end dates and times (and the same duration).

## Modify time entries from the calendar

Time entries can be modified from the calendar in the following ways:

- **Move an entry** – To move a calendar entry to a different position on the same date or a different date, select the entry, and then move it to the desired position on the calendar. The start and end dates and times are updated accordingly.
- **Resize an entry** – To resize a calendar entry, use the indicator at the top or bottom of the entry to increase or decrease its duration. The start and end dates and times are updated accordingly.
- **Edit fields by using a dialog** – Double-tap (or double-click) an editable entry to open a dialog that is named **Edit Time Entry**. This dialog resembles the **Create Time Entry** dialog. All fields for the time entry can be modified. When you finish, select **Save**.

    > [!NOTE]
    > Entries that have a status of **Submitted**, **Approved**, or **Recall Requested** are read-only. A lock symbol on these entries indicates that they can't be edited.

## Delete, submit, or recall time entries from the calendar

### Delete one or more time entries

To delete one or more time entries, follow these steps.

1. Select a time entry that has a status of **Draft** or **Returned**. To delete multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Select **Delete**.
1. In the message that appears, select **Delete** to confirm that you want to delete records.

### Submit one or more time entries

To submit one or more time entries, follow these steps.

1. Select a time entry that has a status of **Draft** or **Returned**. To submit multiple time entries at the same time, select <kbd>Ctrl</kbd> as you select each entry.
1. Select **Submit**. After a short time, the selected entries are submitted, the status is updated to **Submitted**, and the color is changed to blue on the calendar.

### Recall one or more time entries

To recall one or more time entries, follow these steps.

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

The Time Entry Calendar interface helps you track the number of hours that you should log by comparing your total hours with your target hours. Target hours are based on the working hours that are configured for you in Project Operations.

To view the visual snapshot, follow these steps.

1. Go to the Time Entry Calendar for the desired week.
1. Expand the **Charts** section.

    - First, the **Weekly Snapshot** section shows the total hours that were logged for the week and compares them with the target hours for that week.
    - Next, a visualization provides a daily comparison between logged hours and target hours for each day of the week.
    - When you change the timeline, the snapshot is updated to show a daily or monthly comparison.

### Filter time entries by type or status

When the **Charts** section is expanded, a **Legend for calendar entries** section appears at the bottom. In the legend, you can select or clear the selection of specific **Entry Status** or **Type** values to filter the time entries on the calendar.

Application of a filter immediately updates which time entries are visible on the calendar. It also immediately updates the snapshot comparison.

## Declutter mode (preview only)

When time entries are created by using the standard time entry grid, if no start time is explicitly set for them, Project Operations assigns a default start time of 12:00 AM (midnight). This behavior can affect the visual experience when you view those time entries on the calendar, because multiple entries are clustered together at 12:00 AM for each day. To help you view these time entries, the Time Entry Calendar introduces a *declutter mode*.

In declutter mode, the time entries are no longer clustered at 12:00 AM. Instead, they are shown sequentially, starting at the beginning of your working hours. Note that declutter mode just *temporarily* changes where the time entries *appear* on the calendar, so that they are easier to view. It doesn't actually change the start time of the entries.

To use declutter mode, follow these steps.

1. Go to the Time Entry Calendar for the desired week.
1. Confirm that one or more time entries that start at 12:00 AM are visible on the calendar.
1. Turn on the **De-clutter** option. (By default, the option is turned off.)

    The time entries for each day now appear sequentially, starting at the beginning of your working hours (8:00 AM in the following example).

    :::image type="content" source="../media/midnightentriesdecluttered.png" alt-text="Screenshot that highlights location of the De-clutter option and shows the result of turning it on for a user whose working hours begin at 8:00 AM.":::

### Declutter mode behavior

- **Which time entries are decluttered** – Declutter mode affects the display only of time entries that have a start time of 12:00 AM because no start time was explicitly set for them. All existing time entries that a start time was explicitly set for remain as is. There is no change to their display or position on the calendar.
- **How the new position of time entries is determined** – Affected time entries are shown in new positions, based on the user's working hours. The entries are arranged sequentially, based on their **Created On** value. The entry that was created first appears at the beginning of the user's working day. The next entry then immediately follows it.

    For example, a user has working hours from 8:00 AM to 5:00 PM. Two time entries must be decluttered. Each entry has a duration of two hours. Therefore, the entry that was created first is shown from 8:00 AM to 10:00 AM, and the other entry is shown from 10:00 AM to 12:00 PM.

### Making changes to decluttered entries

Declutter mode just *temporarily* changes where time entries *appear* on the calendar, so that they are easier to view. It doesn't actually change the start time of the entries.

However, if you make and save any changes to a time entry while it's shown in its decluttered position, new start and end times that reflect that position are saved for the time entry record.

**Therefore, we don't recommend that you make changes to time entries while declutter mode is turned on.**

[!INCLUDE[footer-include](../includes/footer-banner.md)]
