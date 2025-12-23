---
title: Extending time entries
description: This article provides information about how developers are able to extend the time entry control.
author: mohitmenon
ms.author: mohitmenon
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Extending time entries

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations includes an extendable time entry custom control. This control includes the following features:

- Enter time horizontally over a week
- Totals by day, row, or week
- Copy rows or weeks
- Time entry through HH:mm or HH.hh (automatically converts to HH.hh)
- Import from assignments, bookings, or appointments

Extending time entries is possible in two areas:
- [Add custom time entries for your own use](#add)
- [Customize the weekly Time Entry control](#customize)

## <a name="add"></a>Add custom time entries for your own use

Time entries are a core entity used in multiple scenarios. In April Wave 1 2020, the TESA core solution was introduced. TESA provides a **Settings** entity and a new **Time Entry User** security role. The new fields, **msdyn_start** and **msdyn_end**, which have a direct relation to **msdyn_duration**, were also included. The new entity, security role, and fields allow for a more unified approach to time across multiple products.


### Time source entity
| Field | Description | 
|-------|------------|
| Name  | The name of the Time source entry used as the selection value when creating time entries. |
| Default Time Source [Time Source: isdefault] | By default, only one Time Source can be marked at the default. This allows for entries to default to a time source if one isn't specified. |
|Time Source Type [Time Source: sourcetype] | The source type is an option (Time Entry Source Type) that allows for the association of the time source to an app. Microsoft reserves values greater than 190,000,000.|


### Time entries and the Time source entity
Each time entry is associated to a time source record. This record determines which applications should process the time entry and how.

Time entries are always one contiguous block of time with the start, end, and duration linked.

The logic will automatically update the time entry record in the following situations:

- If two of the three following fields are provided, the third is calculated automatically: 

    - **msdyn_start**
    - **msdyn_end**
    - **msdyn_duration**

- The **msdyn_start** and **msdyn_end** fields are time zone aware.
- Time entries created with only **msdyn_date** and **msdyn_duration** specified will start at midnight. The **msdyn_start** and **msdyn_end** fields will update accordingly.

#### Time entry types

Time entry records have an associated type that defines the behavior in the submission flow for the associated application.

|Label | Value|
|-----|-----|
|On break	|192,355,000|
|Travel	| 192,355,001|
|Overtime	| 192,354,320|
|Work	| 192,350,000|
|Absence	| 192,350,001|
|Vacation	| 192,350,002|


## <a name="customize"></a>Customize the weekly Time entry control
Developers can add additional fields and lookups to other entities, and implement custom business rules to support their business scenarios.

### Add custom fields with lookups to other entities
There are three main steps to adding a custom field to the weekly time entry grid.

1. Add the custom field to the **Quick create** dialog box.
2. Configure the grid to show the custom field.
3. Add the custom field to the **Row edit** or **Time entry edit** page, as appropriate.

Make sure that the new field has the required validations on the **Row edit** or **Time entry edit** page. As part of this task, lock the field, based on the status of the time entry.

When you add a custom field to the **Time entry** grid and then create time entries directly in the grid, the custom field for those entries is automatically set so that it matches the row. 

### Add the custom field to the Quick create dialog box
Add the custom field to the **Quick create: Create Time Entry** dialog box. Users can then enter a value when they add time entries by selecting **New**.

### Configure the grid to show the custom field
There are two ways add a custom field to the **Weekly time entry** grid.

- Customize the **My Weekly Time Entries** view, and add the custom field to it. You can specify the position and size of the custom field in the grid by editing the properties in the view.
- Create a new custom time entry view, and set it as the default view. This view should contain the **Description** and **External comments** fields in addition to the columns that you want the grid to include. You can specify the position, size, and default sort order of the grid by editing the properties in the view. Next, configure the custom control for this view so that it's a **Time Entry Grid** control. Add the control to the view, and select it for **Web**, **Phone**, and **Tablet**. Next, configure the parameters for the **Weekly time entry** grid. Set the **Start date** field to **msdyn\_date**, set the **Duration** field to **msdyn\_duration**, and set the **Status** field to **msdyn\_entrystatus**. The **Read-only Status List** field is set to **192350002 (Approved)**, **192350003 (Submitted)**, or **192350004 (Recall Requested)**.

### Add the custom field to the appropriate edit page
The pages that are used to edit a time entry or a row of time entries can be found under **Forms**. The **Edit entry** button in the grid opens the **Edit entry** page, and the **Edit row** button opens the **Row edit** page. You can edit these pages so that they include custom fields.

Both options remove some out-of-box filtering on **Project** and **Project Task** entities, so that all lookup views for the entities are visible. Out of the box, only the relevant lookup views are visible.

You must determine the appropriate page for the custom field. Most likely, if you added the field to the grid, it should go on the **Row edit** page that is used for fields that apply to the whole row of time entries. If the custom field has a unique value in the row every day (for example, if it's a custom field for the end time), it should go on the **Time entry edit** page.

To add the custom field to a page, drag a **Field** element into the appropriate position on the page, and then set its properties.

### Add new option set values
To add option set values to an out-of-box field, follow these steps:

1. Open the editing page for the field, and then, under **Type**, select **Edit** next to the option set.
2. Add a new option that has a custom label and color. If you want to add a new time entry status, the out-of-box field is named **Entry Status**.

### Designate a new time entry status as read-only
To designate a new time entry status as read-only, add the new time entry value to the **Read-only Status List** property. Be sure to add the number, not the label. The editable part of the time entry grid will now be locked for rows that have the new status. To set the **Read-only Status List** property differently for different **Time Entry** views, add the **Time entry** grid in a view's **Custom controls** section, and configure the parameters as appropriate.

Next, add business rules to lock all the fields on the **Row edit** and **Time entry edit** pages. To access the business rules for these pages, open the form editor for each page, and then select **Business rules**. You can add the new status to the condition in the existing business rules, or you can add a new business rule for the new status.

### Add custom validation rules
You can add two types of validation rules for the **Weekly time entry** grid experience:

- Client-side business rules that work on pages
- Server-side plug-in validations that apply to all time entry updates

#### Client-side business rules
Use business rules to lock and unlock fields, enter default values in fields, and define validations that require information only from the current time entry record. To access the business rules for a page, open the form editor, and then select **Business rules**. You can then edit the existing business rules or add a new business rule.

#### Server-side plug-in validations
You should use plug-in validations for any validations that require more context than is available in a single time entry record. You should also use them for any validations that you want to run on inline updates in the grid. To complete the validations, create a custom plug-in on the **Time Entry** entity.

### Limits
Currently, the **Time entry** grid has a size limit of 500 rows. If there are more than 500 rows, the excess rows won't be show. There is no way to increase this size limit.

### Copying time entries
Use the view **Copy Time Entry Columns** to define the list of fields to copy during time entry. **Date** and **Duration** are required fields and shouldn't be removed from the view.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
