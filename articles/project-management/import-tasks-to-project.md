---
# required metadata

title: Import tasks into a project (Preview)
description: Learn how to import tasks into a project efficiently. Reuse tasks from existing projects to streamline your workflow and save time.
author: dishantpopli
ms.author: dishantpopli
ms.date: 02/02/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Import tasks into a project (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

By using this feature, you can speed up project setup by reusing tasks from one or more projects that you already have access to. This capability provides a selective, flexible alternative to copying an entire project or manually rebuilding a work breakdown structure (WBS).

## Import tasks

To import tasks, follow these steps:

1. Go to the target project where you want to import tasks.
1. Select **Import tasks** from the project ribbon.
1. Choose the source project.
1. Select the tasks and select **Add** to import the tasks.

> [!NOTE]
> - Unlike copy project, a target project can have existing work break down structure.
> - You can import all or selected tasks from one or more projects.
> - The imported tasks are appended to the list of tasks.

## Imported items

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
> The process copies all tasks under the default bucket of the target project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
