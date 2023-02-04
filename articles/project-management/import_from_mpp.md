---
title: Import Projects from Microsoft Project Desktop Client
description: This article provides information about creating projects by importing Project Desktop Files
author: ruhercul
ms.date: 02/02/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Importing Projects from Micrsoft Project Desktop Client

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Project Operations allows Project Managers the ability to import their Project Deskto Files (.MPP) to create projects.  

## Importing a file to create a new Project
To import a new project from a Project Desktop Client file:
1. Navigate to the **Projects** view.
2. From the ribbon, select **Import > Import from MPP**.
3. Update the required **Work Hour Template**, **Project Manager** and **Schedule Mode**.
4. From the dialog, select **Choose File** to choose a file to import.
5. Browse to the .mpp file you want to import, and then select Open.
6. Once a file has been chosen, select **Import** to start the import process.
7. After the Project has been successfully created, review the validation summary.  It will summarize any of the items in the file that have been excluded from the import based on items outlined below.

## Unsupported Desktop Client Capabilities in the Import
Project for the web is great for most projects, but it isn't a complete replacement for Project desktop. The following features aren't supported, and can't be migrated. Before you begin, you should evaluate your project and make sure it doesn't rely on these features.

Note: This list may not be exhaustive. If your new Project for the web project is missing elements or data, they may rely on an unsupported feature that is not listed.

- Baseline  
-	Constraints that aren't imported:
  o 	As late as possible
  o	  Start no later than
  o	  Finish no later than
  o	  Must finish on
  o	  Must start on
-	Cross-project dependencies
-	Deadlines  
-	Formulas
-	Inactive tasks  
-	Links that aren't imported:
  --	  Start-Start
  o	  Finish-Finish
  o	  Start-Finish  
-	Manual tasks  
-	Null tasks
-	Project-level custom fields
-	Recurring tasks  
-	Resources 
-	Schedule from setting  
-	Subprojects

## Work breakdown structure (WBS) Limits
In addition to the unsupported capabilities above, the WBS must conform to the existing limits, described here, https://learn.microsoft.com/en-us/dynamics365/project-operations/project-management/create-wbs#project-limitations.
