---
title: Extending time entries
description: This topic provides information about how developers are able to extend the time entry control.
author: stsporen
ms.date: 10/08/2020
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---

# Extending time entries

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

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
Each time entry is associated to a time source record. This record determines how and which applications should process the time entry.

Time entries are always one contiguous block of time with the start, end, and duration linked.

The logic will automatically update the time entry record in the following situations:

- If two of the three following fields are provided, the third is calculated automatically: 

    - **msdyn_start**
    - **msdyn_end**
    - **msdyn_duration**

- The fields, **msdyn_start** and **msdyn_end** are timezone aware.
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

1.	Add the custom field to the quick create dialog box.
2.	Configure the grid to show the custom field.
3.	You’ll likely want to add the custom field to either the row edit or the time entry edit forms, as appropriate.

You must also make sure that the new field has the required validations in the row or cell edit forms. As part of this step, you must lock the field based on the time entry status.

Once you add a custom field to the time entry grid, any time entries which are created directly through the grid will automatically have these custom fields set to match the row. 


### Add the custom field to the quick create dialog box
You must add the custom field to the **Create Time Entry** Quick Create form so that users can enter a value for it when they add time entries by using the New button.

### Configure the grid to show the custom field
There are two ways add a custom field to the weekly time entry grid. The first option is to customize the My Weekly Time Entries view and add the custom field to it. You can choose the position and size of the custom field in the grid by editing those properties in the view.
The second option is to create a new custom time entry view and set it as the default view. This view should contain the Description and External Comments fields, in addition to the columns that you want to have in the grid. You can choose the position, size, and default sort order of the grid by editing those properties in the view. Next, configure the custom control for this view so that it's a Time Entry Grid control. Add this control to the view, and select it for web, phone, and tablet. Next, configure the parameters for the weekly time entry grid. Set the Start Date field to msdyn_date, set the Duration field to msdyn_duration, and set the Status field to msdyn_entrystatus. The Read-only Status List field is set to 192350002 (Approved),192350003 (Submitted),192350004 (Recall Requested).

### Add the custom field to the appropriate edit forms
The forms that are used for editing a time entry or row of time entries can be found under “Forms”. The grid “Edit entry” button opens the “Edit Entry Form” and the “Edit row” button opens the “Row Edit Form”. These forms can be edited to include custom fields.

Both options will remove some out-of-box filtering on Project and Project Task entities, so that all lookup views for the entities will be visible. Out of the box, only the relevant lookup views are visible.

You must determine the appropriate form for the custom field. Most likely, if you added the field to the grid, it should go in the row edit form that is used for fields that apply to the whole row of time entries. If the custom field has a unique value every day in the row, such as a custom field for End time, it should go in the cell edit form.

To add the custom field to a form, drag a Field element into the appropriate position on the page, and then set its properties. 

### Add new option set values
To add option set values to an out-of-box field, open the editing page for the field, and then, under Type, select Edit next to the option set. Next, add a new option that has a custom label and color. If you want to add a new time entry status, the out-of-box field is named Entry Status, not Status.

### Designate a new time entry status as read-only
To designate a new time entry status as read-only, add the new time entry value (the number, not the label) to the Read-only Status List property. The editable part of the time entry grid will be locked for rows that have the new status. Note that you can have the Read-only Status List property set differently for different Time Entry views by adding the Time Entry Grid under the view’s “Custom Controls” section, and configuring the parameters appropriately. 
Next, add business rules to lock all the fields on the Time Entry Row Edit and Time Entry Edit forms. You can access the business rules for these forms by opening the form editor for the page and then selecting Business Rules. You can add the new status to the condition in the existing business rules, or you can add a new business rule for the new status.


### Add custom validation rules
There are two types of validation rules that you can add for the weekly time entry grid experience: 1) Client-side business rules that work in forms 2) Server-side plug-in validations that apply to all time entry updates.

#### Business rules
Use business rules to lock and unlock fields, enter default values in fields, and define validations that require information only from the current time entry record. You can access the business rules for a form by opening the form editor, and then selecting Business Rules. You can then edit the existing business rules or add a new business rule. 

#### Plug-in validations
You should use plug-in validations for any validations that require more context than is available in a single time entry record, or for any validations that you want to run on inline updates in the grid. To complete the validation, create a custom plug-in on the Time Entry entity.

### Limits
The time entry grid currently has a size limit of 500 rows. If there are more than 500 rows, the excess ones won’t be displayed. There is no way to increase this size limit. 

### Copying time entries
Use the view **Copy Time Entry Columns** to define the list of fields to copy during time entry. **Date** and **Duration** are required fields and shouldn't be removed from the view.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
