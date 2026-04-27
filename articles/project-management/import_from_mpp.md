---
title: Import projects from the Microsoft Project desktop client
description: This article explains how to create projects by importing Microsoft Project desktop files.
author: dishantpopli
ms.date: 10/28/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Import projects from the Microsoft Project desktop client

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations lets project managers import their Microsoft Project desktop client files (.mpp files) to create projects.

## Import a file to create a new project

To import a new project from a Project desktop client file, follow these steps:

1. Open the **Projects** view.
1. On the toolbar, select **Import \> Import from MPP**.

    ![My Active Projects list.](media/importribbonaction.png)

1. Update the **Work hour template**, **Project manager**, **Schedule mode**, and **Contracting Unit** fields as required.
1. Select **Choose File**, browse to the .mpp file that you want to import, and then select **Open**.
1. Select **Import** to start the import process.
1. After the project is successfully created, review the validation summary. The summary indicates whether any items in the file were excluded from the import. For example, the following screenshot shows an example where nine resources were removed from the import.

    ![File import and validation dialog box.](media/importsummary.png)

1. Select **Go to project** to view the project.

## Import a file to an existing project with no WBS

A project without a WBS indicates that you created the project but didn't access the Task tab. Opening the Task tab automatically generates a blank WBS.

To import to an existing project with no WBS from a Project desktop client file, follow these steps:

1. Open the **Projects** view.
1. On the toolbar, select **Import \> Import from MPP**.
1. Select the project you want to import into. Only eligible projects appear in the list.
1. As the project is already created, all fields are locked and can't be edited.
1. Select **Choose File**, browse to the .mpp file that you want to import, and then select **Open**.
1. Select **Import** to start the import process.
1. After the project is successfully created, review the validation summary. The summary indicates whether any items in the file were excluded from the import. For example, the following screenshot shows an example where nine resources were removed from the import.

    ![File import and validation dialog box.](media/importsummary.png)

1. Select **Go to project** to view the project.


## Limitations
The following sections describe limitations of Import from MPP. 

### Unsupported desktop client capabilities in the import

Project for the web is great for most projects, but it isn't a complete replacement for Project desktop. Some features aren't supported and can't be migrated. Therefore, before you begin, evaluate your project and make sure it doesn't rely on them. For a list of these features, see [Features that don't migrate](https://support.microsoft.com/office/move-your-project-from-project-desktop-to-project-for-the-web-143ab391-002e-451a-aedb-3b6fa1f6ab8b#bkmk_featuresthatdontmigrate).

> [!NOTE]
> This list might not be exhaustive. If your new Project for the web project is missing elements or data, they might rely on an unsupported feature that isn't listed.

### Work breakdown structure limits

In addition to the unsupported capabilities described in the previous section, the work breakdown structure (WBS) must conform to the [existing limits](project-and-task-limitations.md).

### Project custom fields

If you customize the project main page by adding required fields, you must provide default values for those fields. Otherwise, errors occur when you import files to create new projects. Customization of the import dialog box isn't currently supported.

### Existing projects with WBS

If a project already contains a WBS—even if it's blank—you can't import tasks from an MPP file.
