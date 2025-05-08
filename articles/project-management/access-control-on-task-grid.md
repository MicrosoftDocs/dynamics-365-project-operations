---
title: Access control on task grid 
description: Learn how to control access on task grid to restrict unnecessary changes
author: dishantpopli
ms.author: dishantpopli
ms.date: 05/06/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Access control on task grid

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations offers the ability to control user access to the task grid. Users can be granted full access, read-only access, or customized permissions for creating, updating, and deleting tasks. These permissions can be configured at both the user level and the project team member level.


## User configuration

A resource might be included in the project team or not. If the resource isn't part of the project, their access to the task grid can be controlled through settings on the **System user** page. At the system user level, there are two types of permissions that can be assigned to a user.

| **Permission** | **Description** |
| --- | --- |
| **Read Only** | The resource has read-only access to the task grid and isn't allowed to make any changes.|
| **Full Access** | The resource has full access to the task grid and can perform all Create, Update, and Delete operations.|

The following screenshots show how to configure the permissions on system user page.

:::image type="content" source="media/set-permissions-on-system-user.png" alt-text="Screenshot that shows project permissions in system user page.":::

:::image type="content" source="media/permissions-in-system-user.png" alt-text="Screenshot that shows types of permissions for system user.":::

> [!IMPORTANT]
> By default, all users are given **Read-Only** access.

## Project team member configuration

A resource who is part of the project team can have their ability to modify the task grid restricted by adjusting settings on the Project Team Member page. At the project team level, there are three types of permissions that can be assigned to a resource. 

| **Access Type** | **Description** |
| --- | --- |
| **Read Only** | The resource has read-only access to the task grid and isn't allowed to make any changes.|
| **Full Access** | The resource has full access to the task grid and can perform all Create, Update, and Delete operations.|
| **Custom** | The resource can be granted customized access permissions for create, update, and delete actions.|

The following screenshots show how to configure the permissions on project team member page.

:::image type="content" source="media/set-permissions-on-project-team-member.png" alt-text="Screenshot that shows project permissions in project team member page.":::

:::image type="content" source="media/permission-in-project-team-member.png" alt-text="Screenshot that shows types of permissions for project team member.":::

The following screenshots show how to configure custom permissions for project team member.

:::image type="content" source="media/custom-permissions-in-project-team-member.png" alt-text="Screenshot that shows custom permissions for project team member.":::

:::image type="content" source="media/edit-custom-permissions-in-project-team-member.png" alt-text="Screenshot that shows how to edit custom permissions for project team member.":::

> [!IMPORTANT]
> By default, all project team members are assigned **Full Access**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
