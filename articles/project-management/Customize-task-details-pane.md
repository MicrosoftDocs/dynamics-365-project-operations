---
title: Customize task details pane 
description: Learn how you can customize task details pane.
author: dishantpopli
ms.author: dishantpopli
ms.date: 04/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Customize task details pane

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Out of the box, Project Operations uses Project for the web to display task details inside an embedded experience. Although powerful, this task details pane is **not customisable**, which limits users to add their customizations on the task.
The **customisable task details pane** addresses these gaps by allowing you to use a Dataverse-backed, model-driven experience that you control.

## What is the customisable task details pane?

The feature is controlled by an **Organization level setting** and when enabled, the customisable task details pane opens a **custom side pane** hosted in Dataverse.

When a user selects the **information (i)** icon next to a task in the task grid:

- If the feature is enabled, a customised side pane opens. Users can click on overflow button and still access the native Project for the web task details pane.
- If the feature is disabled, the default Project for the web task details pane opens.


## Use the custom task details pane (users)

Once enabled:

1. Open a project  
2. Go to the **task grid**  
3. Select the **information (i)** icon next to a task  
4. The custom task details pane opens in a side pane  

From the pane, you can:

- View and edit task fields
- Save changes and close the pane


## Data sync and behaviour

All edits made in the custom task details pane:

- Are saved using Project Scheduling Service (PSS)  
- Automatically sync back to Dataverse  
- Update derived and calculated fields in the UI  

If an error occurs (for example, due to validation or permissions), the system displays an error message so users know what went wrong.


## Access control and validations

The custom task details pane respects existing access controls:

- Users can only edit fields they already have permission to edit  
- Task grid security and access are honoured 
