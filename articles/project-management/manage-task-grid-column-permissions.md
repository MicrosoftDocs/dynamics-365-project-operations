---
title: Manage task grid column permissions
description: Learn how to use column permission templates to control which project task columns users can edit in Microsoft Dynamics 365 Project Operations.
author: dishantpopli
ms.author: dishantpopli
ms.reviewer: johnmichalak
ms.date: 10/05/2026
ms.topic: how-to
ms.custom: 
    - bap-template

---

# Manage task grid column permissions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Task grid column permissions let you limit which project task columns a user can edit. Administrators create reusable column permission templates and assign them as an organization default or to individual users. Project managers can assign a different template to a team member for a specific project.

## Key concepts

Column permissions refine the existing task grid permission model. They don't grant access to a project or replace a user's task grid permission.

- **Task grid permission** controls whether a user can create, update, or delete project tasks.
- **Column permission template** defines which supported task columns are editable or read-only.
- **Organization assignment** provides the default template for the environment.
- **User assignment** applies across projects unless a project-specific assignment exists.
- **Project team member assignment** applies only to that team member on the selected project.

For each supported column, the template uses **Is Editable** to determine access. Set the value to `Yes` to allow edits or `No` to make the column read-only.

### Template precedence

Dynamices 356 Project Operations uses the first assigned template in the following order.

| Priority | Assignment | Scope |
|----------|------------|-------|
| 1 | Project team member | One user on one project |
| 2 | User | One user across projects without a project team member assignment |
| 3 | Organization | Users without a project or user assignment |

If no template is assigned at any level, columns remain editable for a user who already has update permission. A higher-priority template replaces the lower-priority template; Project Operations doesn't merge their column settings.

> [!IMPORTANT]
> A column permission template can't give a user more access than their task grid permission. If a user doesn't have update permission, the task columns remain read-only even when the template marks them editable.

## Prerequisites

- To create templates or set the organization and user assignments, you need permission to manage the corresponding Project Operations configuration records.
- To assign a template to a project team member, you need permission to update that team member record.
- Users need access to the project and an appropriate task grid permission before column permissions can allow edits.

## Create a column permission template

To create a reusable template for a job function or access profile, follow these steps:

1. Go to **Settings** > **General** > **Column permission templates**.
1. Select **New**.
1. In **Name**, enter a descriptive template name.
1. In **Configuration type**, select `Task Column Access Config`.
1. Select **Save**.
1. In **Project Task Config Details**, find each column that you want to configure.
1. Set **Is Editable** to `Yes` for columns that users can edit and to `No` for columns that must remain read-only.
1. Select **Save**.

Project Operations populates the template with its supported task columns. After you save the template, you can't change its **Configuration type**.

> [!NOTE]
> When support for another task column becomes available, opening the template adds the missing configuration row. A column that isn't present in the template defaults to editable.

## Set the organization template

Use the organization assignment as the default for users who don't have a user or project team member assignment. To set the organization template, follow these steps:

1. Go to **Settings** > **General** > **Parameters**.
1. Open the project parameters record.
1. On the **General** tab, select a template in **Task grid column permissions template**.
1. Select **Save**.

Clear **Task grid column permissions template** to remove the organization assignment. Users without a higher-priority assignment then retain their existing task grid update access for all otherwise editable columns.

## Assign a template to a user

A user assignment applies across the user's projects unless a project team member assignment takes precedence. To assign a template to a user, follow these steps:

1. Go to **Settings** > **General** > **User level column permissions**.
1. Open the user record.
1. On the **User permissions on project** tab, edit the user's permission row.
1. Set **Task grid permission** to the required access level.
1. In **Task grid column permissions template**, select the template.
1. Select **Save**.

Clear **Task grid column permissions template** to make the user fall back to the organization assignment.

## Assign a template to a project team member

Use a project team member assignment when a user needs different column permissions on one project. To assign a template to a project team member, follow these steps:

1. Open the project and select the **Team** tab.
1. Open the project team member record.
1. On the **General** tab, select a template in **Task grid column permissions template**.
1. Select **Save**.

Clear the field to make the team member fall back to the user assignment, or to the organization assignment when no user assignment exists.

Project Operations evaluates the effective template for the current user and project. Columns with **Is Editable** set to `No` are read-only, while permitted columns retain their normal editing behavior. The task form also disables controls for restricted columns.

Column restrictions apply when a task is created or updated. If an operation makes a meaningful change to a restricted column, Project Operations rejects the operation. This enforcement also applies to operations that create or update multiple tasks.

An unchanged restricted value that is resubmitted doesn't count as an edit. During task creation, empty values and system-supplied default values also don't cause the operation to fail.

## Using custom roles

If you use custom roles to assign permissions to users, they might lose access to the plan. To ensure continued access, add the following permissions to your custom roles.

### User accessing the task grid

| Entity | Required permissions |
| --- | --- |
| **msdyn_useraccesspermission** | Read |
| **msdyn_projetteampermission** | Read |
| **msdyn_configurationtemplate** | Read |
| **msdyn_projecttaskconfigdetails** | Read |

### User managing access permissions

| Entity | Required permissions |
| --- | --- |
| **msdyn_useraccesspermission** | Create, Read, Write, Append, Append to, Delete |
| **msdyn_projetteampermission** | Create, Read, Write, Append, Append to, Delete |
| **msdyn_configurationtemplate** | Create, Read, Write, Append, Append to, Delete |
| **msdyn_projecttaskconfigdetails** | Create, Read, Write, Append, Append to, Delete |

## Field reference

| Field | Location | Description |
| ------- | ---------- | ------------- |
| **Name** | **Configuration template** | Identifies the reusable template. |
| **Configuration type** | **Configuration template** | Use `Task Column Access Config` for task column permissions. |
| **Column Display Name** | **Project Task Config Details** | Shows the task column represented by the configuration row. |
| **Is Editable** | **Project Task Config Details** | `Yes` allows edits. `No` makes the column read-only. |
| **Task grid column permissions template** | **Parameters**, user permission, and project team member | Assigns a template at the organization, user, or project level. |
| **Task grid permission** | User permission | Controls the user's broader task grid access. Column permissions can't exceed this access. |

## Known issues

| Issue | Cause | Resolution |
| ------- | ------- | ------------ |
| A user can edit a column that is read-only in the organization template. | A user or project team member template has higher priority. | Review the user's assignment and the project team member record. |
| A user can't edit a column that the template marks editable. | The user doesn't have task grid update permission, or a higher-priority template restricts the column. | Review **Task grid permission** and all three template assignment levels. |
| A newly supported column isn't listed in an existing template. | The template hasn't reconciled its column details since support for the column was added. | Open the template again, and then refresh **Project Task Config Details**. |
| An integration or bulk operation fails while updating tasks. | The operation makes a meaningful change to a column that is read-only for the acting user. | Remove the restricted change or assign an appropriate template before retrying. |
| Clearing an assignment gives the user broader edit access. | No lower-priority template applies, so Project Operations uses backward-compatible task grid access. | Assign an organization template when every applicable user needs a governed default. |
| A recent assignment doesn't appear to take effect. | The current project or task view still has earlier permission information. | Refresh the view or reopen the project after saving the assignment. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
