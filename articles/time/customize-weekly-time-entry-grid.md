---
title: Extending time entries
description: This topic provides information about how developers are able to extend the time entry control.
author: stsporen
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
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

## <a name="add"></a>Add custom time entries for your own use.

Time entries are a core entity used in multiple scenarios. In April Wave 1 2020, the TESA core solution was introduced, which provides a **Settings** entity and a new **Time Entry User** security role. The new fields, **msdyn_start** and **msdyn_end**, which have a direct relation to **msdyn_duration**, were also included. The new entity, security role, and fields allow for a more unified approach to time across multiple products.


### Time Source Entity
| Field | Description | 
|-------|------------|
| Name  | The name of the Time Source entry used as the selection value during time entry creation. |
| Default Time Source [Time Source: isdefault] | By default, only one Time Source may be marked at the default time source. This capability allows for entries to default to a time source if one isn't specified. |
|Time Source Type [Time Source: sourcetype] | The source type is an option (Time Entry Source Type) that allows for the association of the time source to an app. Additional values will be added to this option set as additional applications are added. Microsoft reserves values greater than 190,000,000.|


### Time entries and the Time Source Entity
Each time entry is associated to a time source record. This record determines how and which applications should process the time entry.

Time entries are always one contiguous block of time with the start, end, and duration linked.

The logic will automatically update the time entry record in the following situations:

- If two of the three following fields are provided, the third is calculated automatically 

    - **msdyn_start**
    - **msdyn_end**
    - **msdyn_duration**

- The fields, **msdyn_start** and **msdyn_end** are timezone aware.
- Time entries created with only **msdyn_date** and **msdyn_duration** specified will start at midnight, and **msdyn_start** and **msdyn_end** will be updated accordingly.

#### Time entry types

Time entry records have an associated type that defines behavior in the submission flow for the associated application.

|Label | Value|
|-----|-----|
|On break	|192,355,000|
|Travel	| 192,355,001|
|Overtime	| 192,354,320|
|Work	| 192,350,000|
|Absence	| 192,350,001|
|Vacation	| 192,350,002|



## <a name="customize"></a>Customize the weekly Time Entry control
Developers can add additional fields and lookups to other entities, and implement custom business rules to support their business scenarios.

### Add custom fields with lookups to other entities
There are three main steps to adding a custom field to the weekly time entry grid.

- Add the custom field to the quick create dialog box.
- Configure the grid to show the custom field.
- Add the custom field to either the row edit task flow or the cell edit task flow.

Make sure that the new field has the required validations in the row or cell edit task flow. As part of this step, you must lock the field based on the time entry status.

### Add the custom field to the quick create dialog box
Add the custom field to the **Create Time Entry Quick Create** dialog box. Users can then enter a value when they add time entries by selecting **New**.

### Configure the grid to show the custom field
There are two ways add a custom field to the weekly time entry grid:

  - Customize a view and add a custom field
  - Create a new default custom time entry 


#### **Customize a view and add a custom field**

You can customize the **My Weekly Time Entries** view and add the custom field to it. You can choose the position and size of the custom field in the grid by editing those properties in the view.

#### **Create a new default custom time entry** 

This view should contain the **Description** and **External Comments** fields, in addition to the columns that you want to have in the grid. 

1. Choose the position, size, and default sort order of the grid by editing those properties in the view. 
2. Configure the custom control for this view so that it's a **Time Entry Grid** control. 
3. Add this control to the view, and select it for web, phone, and tablet. 
4. Configure the parameters for the weekly time entry grid. Set the **Start Date** field to **msdyn_date**, set the **Duration** field to **msdyn_duration**, and set the **Status** field to **msdyn_entrystatus**. 
5. For the default view, the **Read-only Status List** field is set to **192350002,192350003,192350004**. The **Row Edit Task Flow** field is set to **msdyn_timeentryrowedit**. The **Cell Edit Task Flow** field is set to **msdyn_timeentryedit**. 
6. You can customize these fields to add or remove read-only status, or to use a different task-based experience (TBX) for row or cell editing. These fields should be bound to a static value.


> [!NOTE] 
> Both options will remove some out-of-box filtering on **Project** and **Project Task** entities so that all lookup views for the entities will be visible. Out-of-the-box, only the relevant lookup views are visible.
You must determine the appropriate task flow for the custom field. Most likely, if you added the field to the grid, it should go in the row edit task flow that is used for fields that apply to the whole row of time entries. If the custom field has a unique value every day, such as a custom field for **End time**, it should go in the cell edit task flow.

To add the custom field to a task flow, drag a **Field** element into the appropriate position on the page, and then set the field properties. Set the **Source** property to **Time Entry**, and set the **Data Field** property to the custom field. The **Field** property specifies the display name on the TBX page. Select **Apply** to save your changes to the field, and then select **Update** to save your changes to the page.

To use a new custom TBX page instead, create a new process. Set the category to **Business Process Flow**, set the entity to **Time Entry**, and set the business process type to **Run process as a task flow**. Under **Properties**, the **Page name** property should be set to the display name for the page. Add all the relevant fields to the TBX page. Save and activate the process. Update the custom control property for the relevant task flow to the value of **Name** on the process.

### Add new option set values
To add option set values to an out-of-box field, open the editing page for the field, and then, under **Type**, select **Edit** next to the option set. Next, add a new option that has a custom label and color. If you want to add a new time entry status, the out-of-box field is named **Entry Status**, not **Status**.

### Designate a new time entry status as read-only
To designate a new time entry status as read-only, add the new time entry value to the **Read-only Status List** property. The editable part of the time entry grid will be locked for rows that have the new status.
Next, add business rules to lock all the fields on the **Time Entry Row Edit** and **Time Entry Edit** TBX pages. You can access the business rules for these pages by opening the business process flow editor for the page and then selecting **Business Rules**. You can add the new status to the condition in the existing business rules, or you can add a new business rule for the new status.

### Add custom validation rules
There are two types of validation rules that you can add for the weekly time entry grid experience:

- Client-side business rules that work in quick create dialog boxes and on TBX pages.
- Server-side plug-in validations that apply to all time entry updates.

#### Business rules
Use business rules to lock and unlock fields, enter default values in fields, and define validations that require information only from the current time entry record. You can access the business rules for a TBX page by opening the business process flow editor for the page and then selecting **Business Rules**. You can then edit the existing business rules or add a new business rule. For even more customized validations, you can use a business rule to run JavaScript.

#### Plug-in validations
Use plug-in validations for any validations that require more context than is available in a single time entry record, or for any validations that you want to run on inline updates in the grid. To complete the validation, create a custom plug-in on the **Time Entry** entity.

### Copying time entries
Use the view **Copy Time Entry Columns** to define the list of fields to copy during entry. **Date** and **Duration** are required fields and shouldn't be removed from the view.
