---
title: Time Entry Configurations
description: Learn about how a system administrator can use the configurations available to modify time entry behavior in Project Operations.
author: mohitmenon
ms.date: 10/16/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time entry configurations in Project Operations

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Time entry configurations let system administrators change how Dynamics 365 Project Operations validates and displays time entries. The available configurations are:

- Set the maximum time entry duration for a day.
- Select the preferred time zone behavior on time entry grids.

To access these configurations, follow these steps:

1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units appears. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. Scroll down to the **Time Entry Configuration** section.

## Set maximum time entry duration for a day

By default, the total time entries in a single day can be at most 24 hours (1,440 minutes). Administrators can now set **Max Daily Duration (in minutes)** to any value between **0** and **1,440** minutes to suit their organization's policies.

Project Operations enforces the limit whenever you create a time entry or modify an existing entry's duration. If the duration exceeds the configured maximum, Project Operations returns an error to ensure entries are correctly updated.

> [!NOTE]
> 24 hours (1,440 minutes) continues to be the default when an administrator doesn't set a preferred max. duration.

## Configure minimum interval for time entry duration

- By default, Project Operations allows time entries in multiples of 1 minute. Administrators can now configure the allowable minimum increment for time entry durations so that time entries follow your organization's time-tracking policies.
- Administrators can set this configuration, named as "Min Interval (In Minutes)" with a value between 1 and 60.

**Example:** If the minimum interval is 15 minutes, valid durations must be in multiples of 15 minutes (for example, 30 minutes, 1 hour 45 minutes, and so on). A duration that isn't an exact multiple of 15 minutes is automatically rounded to the nearest higher multiple.

> [!NOTE]
> 1 minute continues to be the default when no minimum interval is considered.
> When a time entry duration isn't a multiple of the configured minimum interval, the duration **automatically updates to the nearest, higher multiple.**

## Set the preferred time zone behavior on time entry grids

- By default, time entry grids are **time zone aware**. Because of this feature, when a delegate or manager in a different time zone views another user's grid, dates can shift unexpectedly.
- Admins can change this behavior to **Time Zone Independent** so that the same dates show regardless of the viewer's time zone. When you apply this setting, the grid uses the **Date (Time Zone Independent)** field instead of the standard **Date** field.
- You can switch back to time zone aware behavior at any time by using the same configuration.

> [!NOTE]
> Time zone aware behavior continues to be the default when you don't select a preferred configuration.

## Use Outlook meetings as a time entry source

When you turn on this toggle, team members can view Outlook meetings on the [Time Entry Calendar interface](time-entry-calendar.md#create-time-entries-using-outlook-meetings) and use them to create time entries.

> [!NOTE]
> This configuration is only available on environments where the Time Entry Calendar feature is enabled.

- By default, this toggle is off.
- Switch the toggle on to enable this capability. Select **Save**.
- To learn more about creating time entries by using Outlook meetings, see [Time Entry Calendar (Preview)](time-entry-calendar.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
