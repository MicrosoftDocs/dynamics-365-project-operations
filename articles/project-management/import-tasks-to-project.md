---
# required metadata

title: Import tasks to a project
description: This article provides information about how to import tasks to a project.
author: dishantpopli
ms.author: dishantpopli
ms.date: 02/02/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Import tasks to a project

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This feature enables project managers and PMOs to accelerate project setup by reusing tasks (including hierarchy and dependencies) from one or more projects they already have access to and offers a selective, flexible alternative to copying an entire project or manually rebuilding a work breakdown structure (WBS).

## How to import tasks

1. Navigate to the target project where tasks need to be imported.
2. Click on the **Import tasks** button from project ribbon.
3. Select the source project.
4. Select the tasks and click add to import the tasks.

> [!NOTE]
> - Unlike copy project, a target project can have existing work break down structure.
> - All or selected tasks from one or more projects can be imported.
> - The imported tasks are appended to the list of tasks.

## What gets imported
| Display Name | Name |
|---|---|
| Project Task Name | msdyn_subject |
| Notes | msdyn_description |
| Duration | msdyn_duration |
| Effort | msdyn_Effort |
| Outline Level | msdyn_OutlineLevel |
| Link Status | msdyn_LinkStatus |
| Parent Task | msdyn_parenttask |
| Copy View Columns | Custom columns defined in the view |

> [!NOTE]
> All the tasks are copied under default bucket of the target project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
