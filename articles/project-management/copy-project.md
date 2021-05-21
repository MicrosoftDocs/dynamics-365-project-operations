---
# required metadata

title: Copy a project
description: This topic provides information about copying projects in Dynamics 365 Project Operations. 
author: ruhercul
ms.date: 05/21/2021
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

## Project properties

When the project is copied, the values in the following fields are copied:

- Name
- Description
- Customer
- Calendar Template
- Currency
- Contracting Unit
- Project Manager
- Status
- Overall Project Status
- Comments
- Estimates
- Estimated Start Date: This is the date that the project is created from the copy.
- Estimated Finish Date: This date is adjusted based on the start date of the new project that was made from the copy.
- Effort (Hours)
- Estimated Labor Cost
- Estimated Expense Cost
- Estimated Material Cost

> [!NOTE]
> Copy project is a long running operation. Project records, their relevant attributes, and many related entities are also copied. Because of the long running nature of the operation, after the copy starts, the target project page is locked for editing until the copy operation is complete.

## Work breakdown structure

When the project is copied, the entire resource-loaded work breakdown structure is copied. Named resources are replaced with generic resources. If the named resources don't have the same working hours as the generic resource, the schedule will be recalculated and task durations may change.

## Project team members

When a project team is copied from the source project, the generic resources are copied. Generic resource assignments are also maintained as they were in the source project. Named resources will be converted to generic team members.

## Estimates

When the project is copied, resource, expense and material estimate lines are copied from the source project. 

For information on how to programmatically access Copy Project, see [Develop project templates with Copy Project](dev-copy-project.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
