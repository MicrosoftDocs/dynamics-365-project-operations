---
title: Add custom columns to the grid view 
description: Learn how to add a custom column to the grid view on the Tasks tab of a project.
author: dishantpopli
ms.author: dishantpopli
ms.date: 07/10/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Add custom columns to the grid view

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A default set of columns that is available in Microsoft Project for the web provides the relevant data for task scheduling. In addition, users can add columns from the Project Tasks table in Dataverse to the grid view on the **Tasks** tab of a project.

## Add a new column

Before you can add a new column to the grid view, you must add a custom column to the Project Tasks table in Dataverse. Default columns from the Project Tasks table can't be selected for display, even if the columns aren't available for display in the grid view. Learn how to add a column to a table in [How to create and edit columns](/power-apps/maker/data-platform/create-edit-fields).

To add a new column to the grid view, follow these steps:

1. After the custom column is created, select the **Tasks** tab of a project, open the grid view, select **Add column**, and then select **More** on the menu.

    :::image type="content" source="media/etcc-add-column.png" alt-text="Screenshot of the Add column menu on the Tasks tab grid view with the More option.":::

1. In the **More** dialog box, select one or more columns to add to the grid view, and then select **Save**.

    :::image type="content" source="media/etcc-column-choice.png" alt-text="Screenshot of two columns selected in the More dialog box.":::

The custom columns are added to the grid view, and any data in them is shown.

:::image type="content" source="media/etcc-complete.png" alt-text="Screenshot of the two selected custom columns added to the grid view.":::

## Edit data in a custom column

You can modify custom columns directly in the task grid. Additionally, data can be updated through Microsoft Dataverse, by using an API, or via the Microsoft Power Apps interface. Custom columns can also be added to the **Project Task** page in Dynamics 365 apps. There, the data can also be edited.

## Supported custom columns

The following types of columns can be added as custom columns in the grid view:

- **Text**
- **Number** 
- **Date**
- **Choice**
- **Currency**
- **Lookup**

## Limitations on custom columns

> [!IMPORTANT]
> - You can add up to 10 custom columns to the task grid of a project. 
> 

### Number

- The columns must be decimal number columns and not any other type.

### Date

- The columns must be date-only columns, not date, and time columns.
- Time zone adjustment configuration must only be **Time zone independent**.

### Choice

- The columns must be choice columns, not yes/no columns.
- Only 2-25 options in a **Choice** type are supported. Although you can create a custom column of type **Choice** with more than 25 options on the Project Tasks table in Dataverse, the task grid doesn't support displaying it.

### Currency

- Adding a currency custom column consumes an extra column for the currency type, reducing the maximum number of supported custom columns from 10 to 9.
- Every currency custom column on a task shares the same transaction currency, and you can't configure the currency type (USD/INR/EUR) independently for each column.
- Currency values must be between -100,000,000,000 and 100,000,000,000.

### Lookup

- You must have read privileges to the lookup entity that the column refers to.
- You must have write access to the custom lookup field on the Task entity.
- For tables referenced by lookup columns, the supported table logical name length is up to 28 characters, including the publisher prefix, when you use standard generated names and a primary name column with a logical name of 10 characters, such as cr123_name.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
