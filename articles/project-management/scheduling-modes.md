---
title: Scheduling modes
description: Learn how to define and manage scheduling modes in Dynamics 365 Project Operations. Discover fixed duration, effort, and units to optimize project planning.
author: abriccetti
ms.author: abriccetti
ms.date: 02/05/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Scheduling modes

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations provides the ability for organizations to define how they manage changes to key variables in tasks within the work breakdown structure. Based on the specific needs of the organization, project managers can change the scheduling mode when they create a project.

Project Operations offers three scheduling modes:

- Fixed duration (this mode is the default)
- Fixed effort (_Work_)
- Fixed units

The definition of a specific scheduling mode determines which values the following formula impacts:

  Effort  = Duration x Units

When you set a project's scheduling mode, you set one of these values and make it unchangeable. Keeping this value constant prioritizes it and notifies the system not to change it when the other two values change. The following table explains the impacts of selecting a specific mode.

| **In this task**             | **If you revise units**   | **If you revise duration** | **If you revise effort**  |
|----------------------|---------------------------|----------------------------|---------------------------|
| Fixed units task     | Duration is recalculated. | Effort is recalculated.    | Duration is recalculated. |
| Fixed effort task    | Duration is recalculated. | Units are recalculated.    | Duration is recalculated. |
| Fixed duration task  | Effort is recalculated.   | Effort is recalculated.    | Units are recalculated.   |

For more information about the implications of a given mode, see [Change the task type for more accurate scheduling](https://support.microsoft.com/en-us/office/change-the-task-type-for-more-accurate-scheduling-b0b969ad-45bc-4e9e-8967-435587548a72). The article uses the term **Work** instead of **Effort**.

## Change the organization's scheduling mode

Complete the following steps to define the scheduling mode of an organization.

1. Go to **Settings** \> **General** \> **Parameters**, and then select the project parameter.
1. On the **Project Parameters** page, select the default scheduling mode for the organization, and then define the ability for the Project manager to override the setting when creating a new project.

## Change the scheduling mode setting on a project

If an organization allows the Project manager to override the default scheduling mode, the Project manager can make that change when they create a new project. However, after the project is saved, you can't change the scheduling mode.

## Copied projects

Because a project is created when you take the copy project action, the Project manager can't set the scheduling mode. The destination project always defaults to the mode defined at the organizational level.

## Copied tasks

When you copy a task from one project to another, the task inherits the scheduling mode of the destination project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
