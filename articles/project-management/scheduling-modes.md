---
title: Scheduling modes
description: This article provides information about scheduling modes. 
author: abriccetti
ms.author: abriccetti
ms.date: 05/21/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Scheduling modes

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Dynamics 365 Project Operations provides the ability for organizations to define how they manage changes to key variables in tasks within the work breakdown structure. Based on the specific needs of the organization, Project Managers can make changes to the scheduling mode when a project is created.

There are three scheduling modes available in Project Operations:

  - Fixed duration (this is the default mode)
  - Fixed effort (*Work*)
  - Fixed units

The values impacted by the definition of a specific scheduling mode are determined by the following formula:

  Effort  = Duration x Units

When you define a project’s scheduling mode, you are setting one of these values, which then can't be changed. Holding this value as a constant places a priority on that value, which notifies the system not to change it when the other two values change. The following table provides information about the impacts of selecting a specific mode.

| **In this task**             | **If you revise units**   | **If you revise duration** | **If you revise effort**  |
|----------------------|---------------------------|----------------------------|---------------------------|
| Fixed units task     | Duration is recalculated. | Effort is recalculated.    | Duration is recalculated. |
| Fixed effort task    | Duration is recalculated. | Units are recalculated.    | Duration is recalculated. |
| Fixed duration task  | Effort is recalculated.   | Effort is recalculated.    | Units are recalculated.   |

For more information about the implications of a given mode, see [Change the task type for more accurate scheduling](https://support.microsoft.com/en-us/office/change-the-task-type-for-more-accurate-scheduling-b0b969ad-45bc-4e9e-8967-435587548a72). In the article, the term **Work** is used instead of **Effort**.

## Change the organization’s scheduling mode

Complete the following steps to define the scheduling mode of an organization.

1. Go to **Settings** \> **General** \> **Parameters**, and then select the project parameter. 
2. On the **Project Parameters** page, select the default scheduling mode for the organization, and then define ability for the Project manager to override the setting when creating a new project.

## Change the scheduling mode setting on a project

If an organization allows the Project manager to override the default scheduling mode, the Project manager can make that change when they create a new project. However, after the project has been saved, the scheduling mode can't be changed.

## Copied projects

Because a project is created when the copy project action is taken, the Project manager can't set the scheduling mode. The destination project will always default to the mode defined at the organizational level.

## Copied tasks

When a task is copied from one project to another, the task inherits the scheduling mode of the destination project.
