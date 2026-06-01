---
title: Customize task details pane 
description: Learn how you can customize task details pane.
author: dishantpopli
ms.author: dishantpopli
ms.date: 05/08/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Customize task details pane

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

By default, Microsoft Dynamics 365 Project Operations uses Microsoft Project for the web to display task details inside an embedded experience. Although this task details pane is powerful, you can't customize it, which limits you from adding customizations on the task. The **customizable task details pane** addresses these gaps by allowing you to use a Microsoft Dataverse-backed, model-driven experience that you control.

## What is the customizable task details pane?

An organization level setting controls the feature. When you enable it, the customizable task details pane opens a custom side pane hosted in Dataverse.

When a user selects the **information (i)** icon next to a task in the task grid:

- If the feature is enabled, a customized side pane opens. You can select the **Overflow** button and still access the native Project for the web task details pane.
- If the feature is disabled, the default Project for the web task details pane opens.

## Enable the Customize Task Pane feature

To enable the Customize Task Pane feature, follow these steps:

1. Go to **Settings** > **Parameters** > **Feature control** on the ribbon.
1. Find and select the **Enable Customize Task Pane** dates feature in the drop-down list.

## Use the custom task details pane

When you enable this feature:

1. Open a project.  
1. Go to the **Task grid**.  
1. Select the **information (i)** icon next to a task.  
1. The custom task details pane opens in a side pane.

From the pane, you can:

- View and edit task fields.
- Save changes and close the pane.

## Data sync and behavior

All edits you make in the custom task details pane:

- Save by using Project Scheduling Service (PSS).  
- Automatically sync back to Dataverse.  
- Update derived and calculated fields in the UI.  

If an error occurs (for example, due to validation or permissions), the system displays an error message to let you know what went wrong.

## Access control and validations

The custom task details pane respects existing access controls:

- You can only edit fields you already have permission to edit.  
- Task grid security and access are honored.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
