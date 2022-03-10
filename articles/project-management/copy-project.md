---
# required metadata

title: Copy a project
description: This topic provides information about copying projects in Dynamics 365 Project Operations. 
author: ruhercul
ms.date: 03/07/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Copy a project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

With Dynamics 365 Project Operations, you can quickly build new projects by selecting **Copy Project** on the **Projects** form. To copy a project, open the project you want to copy, and then select **Copy project**. The action will copy the following:

- Project properties 
- Work breakdown structure
- Project team members
- Project estimates
- Project expense estimates
- Project material estimates
- Project checklists
- Project Buckets


## Project properties

When the project is copied, the values in the following fields are copied:

|                                                                                                                      | Project Operations Non-Stocked Materials | Project Operations Lite | Project for the Web |
|----------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------|---------------------|
| Name                                                                                                                 | :heavy_check_mark:                       | :heavy_check_mark:      | :heavy_check_mark:  |
| Description                                                                                                          | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Customer                                                                                                             | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Calendar Template                                                                                                    | :heavy_check_mark:                       | :heavy_check_mark:      | :heavy_check_mark:  |
| Currency                                                                                                             | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Contracting Unit                                                                                                     | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Owning Company                                                                                                       | :heavy_check_mark:                       |                         |                     |
| Project Manager                                                                                                      | :heavy_check_mark:                       | :heavy_check_mark:      | :heavy_check_mark:  |
| Status                                                                                                               | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Overall Project Status                                                                                               | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Comments                                                                                                             | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimates                                                                                                            | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimated Start Date: This is the date that the project is created from the copy.                                    | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimated Finish Date: This date is adjusted based on the start date of the new project that was made from the copy. | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Effort (Hours)                                                                                                       | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimated Labor Cost                                                                                                 | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimated Expense Cost                                                                                               | :heavy_check_mark:                       | :heavy_check_mark:      |                     |
| Estimated Material Cost                                                                                              |                                          | :heavy_check_mark:      |                     |


> [!NOTE]
> Copy project is a long running operation. Project records, their relevant attributes, and many related entities are also copied. Because of the long running nature of the operation, after the copy starts, the target project page is locked for editing until the copy operation is complete.

## Work breakdown structure

When the project is copied, the entire resource-loaded work breakdown structure is copied. Named resources are replaced with generic resources. If the named resources don't have the same working hours as the generic resource, the schedule will be recalculated and task durations may change.

## Project team members

When a project team is copied from the source project, the generic resources are copied. Generic resource assignments are also maintained as they were in the source project. Named resources will be converted to generic team members.

> [!NOTE]
> Team members and assignments are not copied in Project for the Web.

## Estimates

When the project is copied, resource, expense and material estimate lines are copied from the source project. 

For information on how to programmatically access Copy Project, see [Develop project templates with Copy Project](dev-copy-project.md).

## Quotes and Contracts
Quotes and Contracts are not linked to the destination project.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
