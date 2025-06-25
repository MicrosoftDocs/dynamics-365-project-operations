---
title: Log time using the Dynamics 365 Time Entry Mobile App (Preview)
description: Learn how to log time by using the new Microsoft Dynamics 365 Time Entry Mobile App (Preview).
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/25/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Log time using the Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing._

This article explains how to log time by using the new Microsoft Dynamics 365 Time Entry Mobile App (Preview).

## Create a time entry

There are multiple ways to create time entries in the Time Entry Mobile App.

### Create a time entry through the Quick Create dialog

To create a time entry through the Quick Create dialog, follow these steps.

1. Sign in to the Power Apps mobile app as your Dynamics 365 Project Operations user.
1. Open **Dynamics 365 Time Entry (Production Ready Preview)**. By default, the **My Time** page is used as the landing page.
1. Select the plus sign button (**&plus;**) at the bottom of the page to open the Quick Create dialog.
1. Enter a value for fields such as **Duration**, **Project**, **Task**, and **Role**.

    > [!NOTE]
    > If you create time entries of the **Work** type by using the app, the **Project** and **Task** fields are required.

1. When you're finished, select **Save time** to create the entry.

### Create a time entry from project assignments through the My Work page

To create a time entry from project assignments by using the **My Work** page, follow these steps.

1. Sign in to the Power Apps mobile app as your Dynamics 365 Project Operations user.
1. Open **Dynamics 365 Time Entry (Production Ready Preview)**. By default, the **My Time** page is used as the landing page.
1. Select **My Work** to open the **My Work** page. If your organization uses assignments in project planning, the page shows a list of projects and project tasks.
1. Select **Create** for the project task that you want to log time entries on. The Quick Create dialog appears. The **Project**, **Task**, and **Role** fields are preset.
1. Modify the value of the **Duration** field and other fields as required, and then select **Save time** to create the entry.

### Create a time entry through the Timer page

To create a time entry by using the **Timer** page, follow these steps.

1. Sign in to the Power Apps mobile app as your Dynamics 365 Project Operations user.
1. Open **Dynamics 365 Time Entry (Production Ready Preview)**. By default, the **My Time** page is used as the landing page.
1. Select **Timer** to open to the **Timer** page.
1. Select the **Start** or **Play** button at the top of the page to begin a new timer. Let it continue for as long as your dedicated work is in progress. Then, when you finish, select **Stop** to end the timer. A timer recording is created. The name includes a timestamp for reference.
1. Select **Create** to convert the timer recording into a time entry. The Quick Create dialog appears. The **Duration** field is preset from the recording.
1. Modify the value of other fields as required, and then select **Save time** to create the entry.

You can also use the **Delete** button to delete any unused timer recordings that are no longer required.

> [!NOTE]
> When a timer recording is ended, the duration is rounded to the nearest minute. Therefore, if any recording lasts less than one minute, the duration is set to one minute by default.

## Modify existing time entries

To modify existing time entries, follow these steps.

1. In the Time Entry Mobile App, open the **My Time** page.
1. Select any day of the week where time entries are present.
1. To edit a draft entry, select the **Edit** button. The **Edit time entry** dialog appears.
1. Modify the value of the fields as required, and then select **Save time**.

## Delete, submit, or recall time entries

### Select time entries

To select time entries for further action, follow these steps.

1. In the Time Entry Mobile App, open the **My Time** page.
1. To select a time entry, tap in the white space for it. Completion of this step for multiple time entries together leads to multi-selection of those entries. In this case, the actions that are available depend on the time entry status of each entry.

    To clear the selection of a time entry, tap the white space for it again.

### Delete time entries

To delete time entries, follow these steps.

1. In the Time Entry Mobile App, open the **My Time** page.
1. Select one or more draft time entries.
1. If all the selected entries are in an editable state (*Draft* or *Returned*), you can delete them by selecting the **Delete** button.

    If any one of the selected entries is read-only (for example, because it's in a *Submitted* or *Approved* state), the **Delete** button doesn't appear.

### Submit or recall time entries

To submit or recall time entries, follow these steps.

1. In the Time Entry Mobile App, open the **My Time** page.
1. Select one or more time entries.
1. Follow one of these steps:

    - If all the selected entries selected are in an editable state (*Draft* or *Returned*), you can submit them by selecting the **Submit** button (arrow).
    - If all the selected entries selected are in a *Submitted* or *Approved* state, you can recall them by selecting the **Recall** button. If you try to recall a time entry that is in an *Approved* state, you're prompted to enter a justification for the recall request.

## Track the completion of logging time

To track the completion of logging time, follow these steps.

1. Sign in to the Power Apps mobile app as your Project Operations user.
1. Open **Dynamics 365 Time Entry (Production Ready Preview)**. By default, the **My Time** page is used as the landing page.
1. Select **My Week** to open the **My Week** page. This page provides two charts that you can use to track day-wise logged hours and the weekly total hours.

## Known accessibility issues

The following accessibility issues are currently being worked on:

- Screen Reader doesn't read out accurate labels for expand, collapse, and pin capabilities on the **My Work** page.
- Screen Reader can't read out the duration values in **My Week** charts and occasionally reads out labels that aren't visible.
- Screen Reader doesn't announce some headings and states for pages.
- Screen Reader focus doesn't return to the calendar control after the calendar is activated from the new time entry dialog.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
