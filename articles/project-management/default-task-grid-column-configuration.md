---
title: Configure default task grid columns
description: Learn how to create reusable grid view templates, set organization and project defaults, enforce restrictions, and synchronize task grids.
author: dishantpopli
ms.author: dishantpopli
ms.reviewer: johnmichalak
ms.date: 10/14/2026
ms.topic: how-to
ms.custom:
  - bap-template

---

# Configure default task grid columns

[!INCLUDE [banner](../includes/banner.md)]

***Applies To:** Project Operations Integrated with ERP, Project Operations Core*

By using grid view templates, administrators and PMO leads can define which supported columns appear on a project's task grid and the order in which they appear. An organization default standardizes new projects, while project managers can select a project-specific template and decide whether users can add columns outside the template. This configuration reduces repeated setup and helps maintain consistent task grid views across projects.

## Key concepts

- **Task grid view template** - A reusable configuration that defines the visible task grid columns and their display order.
- **Organization default template** - The template that applies when a project doesn't specify a project-level template.
- **Project-level template** - The template selected directly on a project. It takes precedence over the organization default.
- **Enforce column restrictions** - A project setting that controls whether users can add columns outside the effective template.
- **Sync from template** - A project action that replaces the current task grid column configuration with the latest configuration from the effective template.

### Template precedence

Project Operations resolves the effective template in the following order.

| Priority | Configuration | Result |
| -------- | ------------- | ------ |
| **1** | The project has a **grid view template** | Dynamics 365 Project Operations uses the project-level template. |
| **2** | The project has no template, and **default grid view template** is set in project parameters | Project Operations uses the organization default template. |
| **3** | Neither level has a template | The task grid uses the platform default columns. |

Only one template applies. Project Operations doesn't merge the project-level and organization default templates.

The effective template is applied when you create a project or select **Sync to default view template**. Editing a template doesn't automatically change the task grid configuration of existing projects.

Projects that existed before you configured this feature remain unchanged until you select a template and synchronize the project. Projects without an effective template continue to use the platform default columns.

### Flexible and enforced column sets

| **Enforce Column Restrictions** value | Behavior |
| ------------------------------------- | -------- |
| **No (Flexible)** | The template supplies the initial column set. Users can add or hide any supported task grid column. |
| **Yes (Enforced)** | Users can hide and restore columns in the template, but they can't add columns outside the template. |

Enforcement applies to all users of the project. If column-level access control is also configured, the default view template controls which columns are visible, and column permissions control which visible columns a user can edit. A column that isn't visible can't be edited.

## Prerequisites

- Publish custom project task columns before you add them to a template.
- To create, edit, activate, deactivate, or delete grid view templates, you need the relevant permissions as given in the following section.

### User using the task grid

| Entity | Required permissions |
| --- | --- |
| **msdyn_configurationtemplate** | Read |
| **msdyn_projecttaskconfigdetails** | Read |

### User managing column configurations

| Entity | Required permissions |
| --- | --- |
| **msdyn_configurationtemplate** | Create, Read, Write, Append, Append to, Delete |
| **msdyn_projecttaskconfigdetails** | Create, Read, Write, Append, Append to, Delete |

## Create a grid view template

Create a template for each standard task grid layout that your organization uses. To create a grid view template, follow these steps:

1. Go to **Settings** > **General** > **Task grid view templates**.
1. Select **New**.
1. In **Name**, enter a descriptive template name.
1. In **Configuration type**, select **Default Task Column Config**.
1. Select **Save**.
1. In **Task grid view template**, set each supported column's visibility to **Yes** or **No**.
1. Reorder the visible columns to set their display sequence.
1. Select **Save & Close**.

The column selector includes supported standard and custom project task columns.

> [!NOTE]
> Any newly supported custom column added to the **`msdyn_projecttask`** entity automatically appears in the configuration template.

## Set the organization default template

The organization default determines the starting column configuration for new projects that don't use a different project-level template. To set the organization default template, follow these steps:

1. Go to **Settings** > **Project Parameters**.
1. Open the **General** tab.
1. Select an active template in **Default Task Column Configuration Template**.
1. Select **Save**.

Setting or changing the organization default doesn't update existing projects. The new default applies to new projects and to synchronization on projects that don't have a project-level template.

Clear **Default task column configuration template** to use the platform default columns when a project doesn't specify a template.

## Set a project-level template

Use a project-level template when a project's task grid needs a different layout from the organization default. To set a project-level template, follow these steps:

1. Go to **Projects**, and create or open a project.
1. In **Default View Template**, select an active template.
1. Set **Enforce Column Restrictions** to **Yes** to limit column selection to the template, or set it to **No** to let users add any supported column.
1. Select **Save**.

Changing the template on an existing project updates the template reference but doesn't immediately replace the current task grid columns. Use **Sync to default view template** to apply the selected template.

Clear **Default View Template** to use the organization default. If no organization default exists, the project uses the platform default columns.

## Synchronize a project from its template

Synchronize when you want to apply the latest template configuration or reset ad-hoc column changes. To synchronize a project from its template, follow these steps:

1. Go to **Projects**, and open the project.
1. Open the **Task grid*** and select **Add column**.
1. Select **Sync to default view template**.

> [!IMPORTANT]
> Synchronization overwrites the project's current task grid column configuration. You lose any columns that users added, hid, or reordered outside the template.

## Add custom columns to a template

New custom columns appear the next time you open a template, but Project Operations doesn't add them to existing templates automatically. If you delete a custom column, Project Operations removes it from the template the next time the template is opened or synchronized.

## Field reference

| Field | Location | Description |
| ------- | ---------- | ------------- |
| **Name** | **Configuration template** | Identifies the reusable template. |
| **Configuration type** | **Configuration template** | Use `Default Task Column Config` for task column configurations. |
| **Column Display Name** | **Task Grid View Template** | Shows the task column represented by the configuration row. |
| **Is Visible** | **Project Task Config Details** | `Yes` allows visibility. `No` makes the column hidden. |
| **Order** | **Project Task Config Details** | Decide the order in which the column appears on the task grid. |
| **Default Task Column Configuration Template** | **Parameters**, and **Project** | Assigns a template at the organization or project level. |
| **Enforce Column Restrictions** | **Project** | Restricts available task grid columns to the template when set to **Yes**. |
| **Sync from Template** | **Project** | Replaces the current task grid column configuration with the effective template. |

## Common issues

| Issue | Cause | Resolution |
| ------- | ------- | ------------ |
| **A project uses the platform default columns.** | Neither the project nor project parameters specify a template. | Set organization level **Default Task Column Configuration Template** or select a project-level **Default View Template**. |
| **An existing project doesn't reflect an organization default change.** | Organization default changes don't update existing projects automatically. | Clear the project-level template if necessary, and select **Sync to default view template**. |
| **An existing project doesn't reflect a template edit.** | Existing projects retain their last applied column configuration. | Select **Sync to default view template**, and then refresh the task grid. |
| **A newly selected project template doesn't change the task grid.** | Changing the lookup doesn't automatically overwrite an existing project's columns. | Select **Sync to default view template** to apply the selected template. |
| **A supported column isn't available from the task grid.** | **Enforce Column Restrictions** is set to **Yes**, and the column isn't in the template. | Add the column to the template and synchronize, or set enforcement to **No**. |
| **A custom column doesn't appear in the template.** | The custom column isn't published or the template.. | Publish the column. |
| **A template can't be deleted.** | One or more projects reference the template. | Remove the project references or deactivate the template. |
| **The project uses a different template than expected.** | A project-level template takes precedence over the organization default. | Clear **Default View Template** on the project to use the organization default. |

[!INCLUDE [footer-include](../includes/footer-banner.md)]
