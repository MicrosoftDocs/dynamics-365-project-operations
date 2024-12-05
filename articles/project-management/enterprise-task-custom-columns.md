---
title: Add custom columns to the grid view 
description: This article provides information about how to add a custom column to the grid view in the tasks tab of a project.
author: abriccetti
ms.author: abriccetti
ms.date: 12/05/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Add custom columns to the grid view

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

A default set of columns available in Microsoft Project for the web that provides the relevant data for task scheduling. In addition to these default columns, users can add more columns from the Project tasks table in Microsoft Dataverse to the grid view.

## Add a new column

To add a new column, a user must first add a custom column to the Project Tasks table in Dataverse. Default columns from the table, even the columns that aren't available to display on the tasks grid, can't be selected for display. For instructions on adding a column to a table, see [How to create and edit columns](/power-apps/maker/data-platform/create-edit-fields).

To add a new column, follow these steps.

1. After the custom column is created, go to the **Tasks** tab of a project, open the grid view, select **Add column**, and select **More**.

   ![Adding a custom column](media/etcc-add-column.png)

1. In the dialog box that appears, select one or more columns to add to the grid view, and select **Save**.

   ![Choosing custom columns](media/etcc-column-choice.png)

The custom columns are added to the grid view and any data in the columns displays.

   ![Custom columns added](media/etcc-complete.png)

## Edit data in a custom column

Currently editing data in custom columns from the grid view isn't supported. This data must be updated either directly in Dataverse, via API or the Power Apps UI, or by adding the custom columns to the Project Task form in Dynamics 365 apps and editing it there. The ability to edit data directly in the grid view is planned for future release.

## Custom column limitations

The following types of columns can be added as custom columns in the grid view:
- Text
- Number
- Date (must be date only, not date and time)
- Choice (must be choice, not yes/no)

> [!IMPORTANT]
> A maximum of 10 custom columns can be added to a single project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
