---
# required metadata
title: Scheduling Modes
description: This topic provides information about scheduling modes in  Project Operations. 
author: ruhercul
manager: AnnBe
ms.date: 04/22/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: ruhercul
---

# Scheduling Modes

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Project Operations provides organizations the ability to define their preferred
method of managing the outcome of changes to the key variables in tasks within
the work breakdown structure. Given the specific needs of the organization,
Project Managers can also be granted permission to make changes to this
scheduling mode at the time of project creation.

Project Operations provides three scheduling modes:

-   Fixed Duration (default)

-   Fixed Work

-   Fixed Units

The values impacted by the definition of a specific scheduling mode are governed
by the following formula:

Effort (*Work*) = Duration x Units

When defining a project’s scheduling mode, the user is essentially “fixing” (or
make unchangeable) one of these values. Holding one of these values constant,
places a priority on that value by telling Project Operations not to change it
when the other two values change. The table below summarizes the impacts of
choosing a specific mode.

| **In a**             | **If you revise units**   | **If you revise duration** | **If you revise effort**  |
|----------------------|---------------------------|----------------------------|---------------------------|
| Fixed units task     | Duration is recalculated. | Effort is recalculated.    | Duration is recalculated. |
| Fixed effort task    | Duration is recalculated. | Units are recalculated.    | Duration is recalculated. |
| Fixed duration task  | Effort is recalculated.   | Effort is recalculated.    | Units are recalculated.   |

[Click
here](https://support.microsoft.com/en-us/office/change-the-task-type-for-more-accurate-scheduling-b0b969ad-45bc-4e9e-8967-435587548a72)
to read more about the implications of a given mode. Please note, in this
article you will see reference to “Work” not “Effort”.

Changing the organization’s scheduling mode
-------------------------------------------

To define the scheduling mode of an organization, navigate to **Settings** \>
**General** \> **Parameters**, then select the Project Parameter. From the
project parameter main form, choose the default scheduling mode for the
organization and then define ability for the Project Manager to override the
setting when creating a new project.

Changing the scheduling mode setting on a project
-------------------------------------------------

If an organization enables the ability for the Project Manager to override the
default scheduling mode, when a new project is created a Project Manager will be
able to change the default mode prior to saving the project. Please note, once
the project has been saved, the scheduling mode cannot be saved.

Copying Projects
----------------

Since a project is created at the time the copy project action is taken, the
project manager does not have the ability to set the scheduling mode, therefore
the destination project will always default to the mode defined at the
organizational level.

Copying Tasks between Projects
------------------------------

When a task a is copied is copied from one project to the other, the task will
inherit the scheduling mode of the destination project.
