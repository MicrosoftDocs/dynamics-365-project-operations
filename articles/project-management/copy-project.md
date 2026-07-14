---
title: Copy a project
description: This article provides information about copying projects in Dynamics 365 Project Operations. 
author: dishantpopli
ms.date: 04/27/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Copy a project

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

By using Dynamics 365 Project Operations, you can quickly build new projects by selecting **Copy Project** on the **Projects** form. You can copy projects only if they have at least one task. 

To copy a project, follow these steps:

1. Open the project you want to copy.
1. Select **Copy project**. 
1. Select if you want to **Copy to New Project** or **Copy to Existing Project**.

   - When you select **Copy to New Project**, a quick create form appears, presenting a set of options and configurations. These configurations help ensure that your input is included for certain fields that become locked after selection.
   - When you select **Copy to Existing Project**, a dialog box appears. You can select the target project from a list of eligible projects and select the team member copy option.

> [!NOTE]
> Copy project is available for externally scheduled projects.

The action copies the following data:

- Project properties
- Work breakdown structure
- Project team members
- Project Estimates (Labor, Expense, and Material)
- Project checklists
- Project buckets

## Project properties

When you copy the project, the process copies the values in the following fields.

| Field | Project Operations Non-Stocked Materials | Project Operations  Core | Project for the Web |
|-------|------------------------------------------|-------------------------|---------------------|
| Name | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Description | :heavy_check_mark: | :heavy_check_mark: | |
| Customer | :heavy_check_mark: | :heavy_check_mark: | |
| Calendar Template | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Currency | :heavy_check_mark: | :heavy_check_mark: | |
| Contracting Unit | :heavy_check_mark: | :heavy_check_mark: | |
| Owning Company | :heavy_check_mark: | | |
| Project Manager | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Status | :heavy_check_mark: | :heavy_check_mark: | |
| Overall Project Status | :heavy_check_mark: | :heavy_check_mark: | |
| Comments | :heavy_check_mark: | :heavy_check_mark: | |
| Estimates | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Start Date. **Note:** This field specifies the date when the project is created from the copy. | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Finish Date. **Note:** The date in this field is adjusted based on the start date of the new project that you create from the copy. | :heavy_check_mark: | :heavy_check_mark: | |
| Effort (Hours) | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Labor Cost | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Expense Cost | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Material Cost | | :heavy_check_mark: | |

> [!NOTE]
> Copy project is a long running operation. The process copies project records, their relevant attributes, and many related entities. Because of the long running nature of the operation, after the copy starts, the target project page is locked for editing until the copy operation is complete.

## Work breakdown structure

When you copy a project, you also copy the entire resource-loaded work breakdown structure. The process replaces named resources with generic resources. If the named resources don't have the same working hours as the generic resource, the schedule is recalculated, and task durations might change.

## Project team members

When you copy a project team from the source project, you copy the generic resources. The process maintains generic resource assignments as they were in the source project. The process converts named resources to generic team members.

> [!NOTE]
> Project for the Web doesn't copy team members and assignments.

## Estimates

When you copy a project, you also copy resource, expense, and material estimate lines from the source project. 

For information on how to programmatically access Copy Project, see [Develop project templates with Copy Project](dev-copy-project.md).

## Quotes and contracts

Quotes and contracts aren't linked to the destination project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
