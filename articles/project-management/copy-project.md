---
title: Copy a project
description: This article provides information about copying projects in Dynamics 365 Project Operations. 
author: dishantpopli
ms.date: 01/09/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Copy a project

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

With Dynamics 365 Project Operations, you can quickly build new projects by selecting **Copy Project** on the **Projects** form. Projects can only be copied if they have at least one task. To copy a project, open the project you want to copy, and then select **Copy project**. The action copies the following:

- Project properties 
- Work breakdown structure
- Project team members
- Project Estimates (Labor, Expense, and Material)
- Project checklists
- Project buckets

## Project properties

When the project is copied, the values in the following fields are copied.

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
| <p>Estimated Start Date</p><p><strong>Note:</strong> This field specifies the date when the project is created from the copy. | :heavy_check_mark: | :heavy_check_mark: | |
| <p>Estimated Finish Date</p><p><strong>Note:</strong> The date in this field is adjusted based on the start date of the new project that was made from the copy.</p> | :heavy_check_mark: | :heavy_check_mark: | |
| Effort (Hours) | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Labor Cost | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Expense Cost | :heavy_check_mark: | :heavy_check_mark: | |
| Estimated Material Cost | | :heavy_check_mark: | |

> [!NOTE]
> Copy project is a long running operation. Project records, their relevant attributes, and many related entities are also copied. Because of the long running nature of the operation, after the copy starts, the target project page is locked for editing until the copy operation is complete.

## Work breakdown structure

When the project is copied, the entire resource-loaded work breakdown structure is copied. Named resources are replaced with generic resources. If the named resources don't have the same working hours as the generic resource, the schedule is recalculated, and task durations might change.

## Project team members

When a project team is copied from the source project, the generic resources are copied. Generic resource assignments are also maintained as they were in the source project. Named resources are converted to generic team members.

> [!NOTE]
> Team members and assignments aren't copied in Project for the Web.

## Estimates

When the project is copied, resource, expense, and material estimate lines are copied from the source project. 

For information on how to programmatically access Copy Project, see [Develop project templates with Copy Project](dev-copy-project.md).

## Quotes and contracts

Quotes and contracts aren't linked to the destination project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
