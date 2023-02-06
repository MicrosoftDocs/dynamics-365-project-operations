---
title: Import Projects from Microsoft Project Desktop Client
description: This article provides information about creating projects by importing Project Desktop Files
author: ruhercul
ms.date: 02/02/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Importing Projects from Microsoft Project Desktop Client

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project Operations provides Project Managers the ability to import their Microsoft Project desktop files (.MPP) to create projects.  

## Importing a file to create a new Project
To import a new project from a Project desktop client file, complete the following steps.

1. Navigate to the **Projects** view.
1. From the ribbon, select **Import > Import from MPP**.
![Screenshot of the My active projects list](media/importribbonaction.png)
1. Update the required **Work Hour Template**, **Project Manager** and **Schedule Mode**.
![Screenshot example of the Import from MPP dialog](media/importdialog.png)
1. Select **Choose File** to choose a file to import.
1. Browse to the .mpp file you want to import, and then select Open.
![Screenshot the File open dialog](media/filebrowser.png)
1. Once a file has been chosen, select **Import** to start the import process.
1. After the Project has been successfully created, review the validation summary.  It will summarize any of the items in the file that have been excluded from the import based on items outlined below.
![Screenshot example of File import and validataion dialog](media/importsummary.png)
1. Select **Go to Project** to view the project.

## Unsupported Desktop Client Capabilities in the Import
Project for the web is great for most projects, but it isn't a complete replacement for Project desktop. The following features aren't supported, and can't be migrated. Before you begin, you should evaluate your project and make sure it doesn't rely on these features.

> [!Note] 
> This list may not be exhaustive. If your new Project for the web project is missing elements or data, they may rely on an unsupported feature that is not listed.

[Move your project from Project desktop to Project for the web > Features that don't migrate](https://support.microsoft.com/office/move-your-project-from-project-desktop-to-project-for-the-web-143ab391-002e-451a-aedb-3b6fa1f6ab8b#:~:text=1%20Download%20the%20required%20PowerShell%20commands.%202%20Find,Your%20instance%20ID%20with%20the%20ID%20you%20looked)


## Work breakdown structure (WBS) Limits
In addition to the unsupported capabilities above, the WBS must conform to the [existing limits](create-wbs#project-limitations.md).

## Handling Project Custom Fields
If you have customized the project main form with required fields, these fields must have default values to avoid errors when importing files to create new projects. Customization of the import form is currently not supported.
