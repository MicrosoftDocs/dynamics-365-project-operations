---
title: Time entry UI behavior
description: This article provides information about the behavior of the UI for Time Entry. 
author: mohitmenon
ms.date: 10/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time entry UI behavior

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The **Weekly time entry** grid is a custom control that has two main sections, **Dimensions** and **Duration**.

## Keyboard shortcuts

| Action      | Shortcut                |
|------------ |------------------------ |
| New         | Alt + Shift + n         |
| Copy row    | Alt + Shift + c         |
| Edit entry  | Alt + Shift + e         |
| Edit row    | Alt + Shift + Ctrl + e  |
| Open entry  | Alt + Shift + o         |
| Submit      | Alt + Shift + s         |
| Recall      | Alt + Shift + r         |
| Delete      | Alt + Shift + d         |
| Copy week   | Alt + Shift + w         |

## Dimensions

The **Dimensions** section shows the dimensions that you can enter time against. The following dimensions are supported:

- Project
- Project Task
- Role
- Type
- Entry Status

The **Dimensions** section doesn't support inline editing. This section is backed by a view that enables custom fields to be added to the weekly time entry grid.

## Duration

The **Duration** section shows the days of the week as column headers. This section supports inline editing. After you create a time entry row with the appropriate dimensions, you can quickly enter the amount of time that you spent on those dimensions.

## Create a new time entry

To create a new time entry, follow these steps:

1. In the time entry grid, select **New**.
1. In the **Time Entry Quick Create** dialog box, select the time entry date.
1. Enter data for the **Project**, **Project Task**, **Role**, and **Duration** dimensions. Add this information in minutes, hours, or days by typing **h**, **m**, or **d**, together with the number.
1. Enter a description for the entry and any comments that you can share externally regarding time entry.

When you save the entry, the entered values appear in the **Dimensions** section. The information you enter in the **Duration** field appears on the date that you created the time entry for.

Lookup fields are backed by system views. For example, after you enter a project, the **Project Task** field is set to the **Copy** view by default. To create time entries for tasks that aren't assigned to a user, select **Change View** in the lookup dialog box, and then select the **All Active Project Tasks** view.

## Edit a time entry

The weekly time entry grid doesn't show details from some fields on the time entry page, such as **Description** and **External Comments**. Instead, a small triangular indicator appears in the **Duration** cells that have these details.

To edit a time entry, follow these steps:

1. Select the cell you want to update in the time entry.
1. Select **Edit Details** to update the data in the **Time Entry Mainform** pane.

## Edit descriptions and external comments for a week (preview)

The new **Weekly Time Entry Notes** preview feature enables time entry users to view and edit _Description_ and _External Comment_ fields for multiple time entries in a week. For ease of reference, these fields are referred to as "Notes."

### Enable weekly time entry notes

To enable weekly time entry notes, follow these steps:

1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. View the list of organization units. Double-tap or double-click the **Organization Units** row for the columns that aren't links.
1. On **Project Parameters**, select **Feature Control**.
1. Select **Enable Weekly Time Entry Notes**, and then select **OK**. If the text **Disable Weekly Time Entry Notes** appears instead, the feature is already enabled.
1. After you enable the feature, a new **Add Notes** button appears on the action ribbon when the time entry grid loads.

### View and edit notes (description or external comments)

To view and edit notes, follow these steps:

1. Go to **Time Entries**. A new **Add Notes** button is visible on the action ribbon.
1. Select time entries to view or edit notes:
   1. **When no time entries are selected**: You can view or edit notes for all time entries in the week.
   1. **When one or more time entries are selected**: You can view or edit notes for only the selected time entries.
1. Select the **Add Notes** action button to open a dialog where selected time entries are ordered by _Date_, with the option to **filter by Project**, including non-project entries (Absence or Vacation).
1. You can modify the _Description_ and _External Comments_ for editable time entries (Draft, Returned, and so on) from the text box provided. You can view but not edit read-only time entries.
1. When you're done, select **Save notes** to save all changes.

## Copy a time entry row

After you create a row, select **Copy Row** to copy the whole row to a new row. When you copy a row, you also copy dimensions and durations. You can also select **Edit Row** to update dimension values and durations in the **Duration** section.

## Open a time entry

To support optimal and quick entry in the most prominent fields, the weekly time entry grid shows a subset of selected dimensions and time durations. To view all the details of a single time entry, under **Edit Entry**, select **Open**.

## Submit a time entry

You can submit a single time entry or a group of time entries by selecting a block of cells or a whole time entry row, and then selecting **Submit**. Submitted time entries appear as entries that are pending approval on the approvers' **Approval** page. After you submit time entries, you can't edit them.

## Recall a time entry

You can recall time entries that you submitted. You can recall a single time entry, a block of time entries, or a whole row of time entries. You can edit recalled time entries.

## Time entry statuses

The following time entry statuses are available:

- **Draft**: New time entries automatically have a status of **Draft**. Only time entries with a status of **Draft** can be deleted.
- **Submitted**: When you submit a time entry, the status updates to **Submitted**.
- **Approved**: When an approver approves a submitted time entry, the status updates to **Approved**.
- **Returned**: If an approver rejects a time entry, the status updates to **Returned**, and the entry becomes available for correction and resubmission.

## View rejection comments

When an approver rejects a time entry, they might add comments to help the resource understand the reason for the rejection. To view the rejection comments for a time entry, select **Open entry**. The rejection comments are shown in the timeline. The user can respond to the rejection comments before they resubmit the entry.

## Copy a week

After you create a few time entries, you can create multiple time entries at the same time.

To copy a week, follow these steps:

1. In the **Time Entries** form, select **Copy Week** to bulk-create more time entries.
1. In the **Copy** dialog box, in the **From period** section, use the **Start Date** and **End Date** fields to define the date range to copy time entries from.
1. In the **To Period** section, in the **Start Date** field, specify the date to create time entries for.
1. Select **Copy**. For the specified date in the **To period**, a copy of the time entries for the corresponding day of the week in the **From period** is created. For example, Monday's time entry from last week is copied into Monday of the week that is specified as the **To period**.

## Import

The process to import from bookings, assignments, and exchanges uses the same basic steps. You can specify the date range for bookings to import, and then select the bookings to copy into draft time entries.

> [!IMPORTANT]
> As of **May 1, 2025**, the security policy disables the _Import from Exchange Appointments_ functionality.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
