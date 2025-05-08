---
title: Time entry UI behavior
description: This article provides information about the behavior of the UI for Time Entry. 
author: mohitmenon
ms.date: 05/08/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time entry UI behavior

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


The **Weekly time entry** grid is a custom control that has two main sections, **Dimensions** and **Duration**.

## Keyboard shortcuts
| Action     	| Shortcut               	|
|------------	|------------------------	|
| New        	| Alt + Shift + n        	|
| Copy row   	| Alt + Shift + c        	|
| Edit entry 	| Alt + Shift + e        	|
| Edit row   	| Alt + Shift + Ctrl + e 	|
| Open entry 	| Alt + Shift + o        	|
| Submit     	| Alt + Shift + s        	|
| Recall     	| Alt + Shift + r        	|
| Delete     	| Alt + Shift + d        	|
| Copy week  	| Alt + Shift + w        	|

## Dimensions
The **Dimensions** section shows the dimensions that time can be entered against. The following dimensions are supported out-of-the-box:

  - Project
  - Project Task
  - Role
  - Type
  - Entry Status

The **Dimensions** section doesn't allow inline editing. This section is backed by a view that enables custom fields to be added to the weekly time entry grid.

## Duration
The Duration section shows the days of the week as column headers. This section allows inline editing. After a time entry row is created with the appropriate dimensions, users can quickly enter the amount of time that they spent on those dimensions.

## Create a new time entry

1. In the time entry grid, select **New**. 
2. In the **Time Entry Quick Create** dialog box, select the time entry date.
3. Enter data for the **Project**, **Project Task**, **Role**, and **Duration** dimensions. This information should be added in minutes, hours, or days by typing **h**, **m**, or **d**, together with the number. 
4. Enter a description for the entry and any comments that can be shared externally regarding time entry. 

When you save the entry, the entered values appear in the **Dimensions** section. The information entered in the **Duration** field appears on the date that the time entry was created for.

Lookup fields are backed by system views. For example, after a user enters a project, the **Project Task** field is set to the **Copy** view by default. To create time entries for tasks that aren't assigned to a user, select **Change View** in the lookup dialog box, and then select the **All Active Project Tasks** view.

## Edit a time entry 
Details from some fields on the time entry page, such as **Description** and **External Comments**, aren't shown in the weekly time entry grid. Instead, a small triangular indicator appears in the **Duration** cells that have these additional details. 

1. To edit a time entry, select the cell you want to update in the time entry.
2. Select **Edit Details** to update the data in the **Time Entry Mainform** pane. 

## Copy a time entry row
After the row has been created, you can select **Copy Row** to copy the whole row to a new row. When a row is copied in this way, dimensions and durations are also copied. You can also select **Edit Row** to update dimension values and durations in the **Duration** section.

## Open a time entry behavior
To support optimal and quick entry in the most prominent fields, the weekly time entry grid shows a subset of selected dimensions and time durations. To view all the details of a single time entry, under **Edit Entry**, select **Open**.

## Submit a time entry
You can submit a single time entry or a group of time entries by selecting a block of cells or a whole time entry row, and then selecting **Submit**. Submitted time entries appear as entries that are pending approval on the approvers' **Approval** page. After time entries are successfully submitted, they can't be edited.

## Recall a time entry
You can recall time entries that you've submitted. You can recall a single time entry, a block of time entries, or a whole row of time entries. Recalled time entries can be edited.

## Time entry status

- **Draft**: New time entries are automatically assigned a status of **Draft**. Only time entries that have a status of **Draft** can be deleted.
- **Submitted**: When a time entry is submitted, the status is updated to **Submitted**. 
- **Approved**: When a submitted time entry is approved, the status is updated to **Approved**. 
- **Returned**: If a time entry is rejected, the status is updated to **Returned**, and the entry becomes available for correction and resubmission. 

## View rejection comments
When a time entry is rejected by an approver, the approver might add comments to help the resource understand the reason for the rejection. To view the rejection comments for a time entry, select **Open entry**. The rejection comments will be shown in the timeline. The user can respond to the rejection comments before they resubmit the entry.

## Copy week
After a few time entries have been created, users can create multiple time entries at the same time.

1. In the **Time Entries** form, select **Copy Week** to bulk-create additional time entries. 
2. In the **Copy** dialog box, in the **From period** section, use the **Start Date** and **End Date** fields to define the date range to copy time entries from. 
3. In the **To Period** section, in the **Start Date** field, specify the date to create time entries for. 
4. Select **Copy**. For the specified date in the **To period**, a copy of the time entries for the corresponding day of the week in the **From period** is created. For example, Monday's time entry from last week is copied into Monday of the week that is specified as the **To period**.

## Import
The same basic process is used to import from bookings, assignments, and exchanges. You can specify the date range that bookings are imported from and then explicitly select the bookings that should be copied into draft time entries. 

> [!IMPORTANT]
> As of **May 1, 2025**, the security policy has changed to disable the _Import from Exchange Appointments_ functionality.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
