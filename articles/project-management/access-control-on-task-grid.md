---
title: Access control on the task grid 
description: Learn how you can control access to the task grid to limit unnecessary changes.
author: dishantpopli
ms.author: dishantpopli
ms.date: 09/08/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Access control on the task grid

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations provides control over user access to the task grid. You can grant users full access, read-only access, or customized permissions for creating, updating, and deleting tasks. Configure these permissions at both the user level and the project team member level.

## User configuration

If a resource isn't part of a project team, control their access to the task grid through settings on the **System user** page. At the system user level, assign two types of permissions to resources.

| Permission | Description |
|---|---|
| Read only | The resource has read-only access to the task grid and can't make any changes. |
| Full access | The resource has full access to the task grid and can perform all Create, Update, and Delete operations. |

To configure permissions at the system user level, follow these steps:

1. On the **System user** page, on the Action Pane, select **Project user permissions**.

    :::image type="content" source="media/set-permissions-on-system-user.png" alt-text="Screenshot of the Project user permissions button on the System user page.":::

1. In the **Project user permissions** dialog, in the **Access Level** field, select a value.


> [!NOTE]
> By default, all users have **read-only access**.

## Project team member configuration

If a resource is part of a project team, you can limit their ability to modify the task grid through settings on the **Project Team Member** page. At the project team member level, you can assign three types of permissions to resources.

| Access type | Description |
|---|---|
| Read only | The resource has read-only access to the task grid and isn't allowed to make any changes. |
| Full access | The resource has full access to the task grid and can perform all Create, Update, and Delete operations. |
| Custom | The resource has customized access permissions for Create, Update, and Delete operations. |

To configure permissions at the project team member level, follow these steps:

1. On the **Project Team Member** page, the **Access Level** field shows the current permission type that's assigned to the resource. To change the permission type, select **User permissions** on the Action Pane.

    :::image type="content" source="media/set-permissions-on-project-team-member.png" alt-text="Screenshot of the location of the Access Level field and the User permissions button on the Project Team Member page.":::

1. In the **Set Permission** dialog, select a value in the **Access Level** field.

1. If you select **Custom** in the **Access Level** field, a **Permissions** grid appears in the dialog. Select **Edit** to open the **Project Team Member Permission** page, where you can modify the custom permissions.

> [!NOTE]
> By default, all project team members have **full access**.

## Using custom roles

If you use custom roles to assign permissions to users, they might lose access to the plan. To ensure continued access, add the following permissions to your custom roles.

### User accessing the task grid

| Entity | Required permissions |
|---|---|
| **msdyn_useraccesspermission** | Read |
| **msdyn_projetteampermission** | Read |

### User managing access permissions
| Entity | Required permissions |
|---|---|
| **msdyn_useraccesspermission** | Create, Read, Write, Append, Append to, Delete |
| **msdyn_projetteampermission** | Create, Read, Write, Append, Append to, Delete |



[!INCLUDE[footer-include](../includes/footer-banner.md)]
