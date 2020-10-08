---
title: Develop project templates with Copy Project
description: This topic provides information about how to create project templates using the Copy Project custom action.
author: stsporen
manager: Annbe
ms.date: 10/07/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: stsporen
---

# Develop project templates with Copy Project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations supports the ability to copy a project and revert any assignments back to the generic resources that represent the role. Customers can use this functionality to build basic project templates.

When you select **Copy Project**, the status of the target project is updated. Use **Status Reason** to determine when the copy action is complete. Selecting **Copy Project** also updates the start date of the project to the current start date if no target date is detected in the target project entity.

## Copy Project custom action 

### Name 

**msdyn_CopyProjectV2**

### Input parameters
There are three input parameters:

| Parameter          | Type   | Values                                                   | 
|--------------------|--------|----------------------------------------------------------|
| ProjectCopyOption  | String | **clearTeamsAndAssignments** or **removeNamedResources** |
| SourceProject      | Entity Reference | Source Project |
| Target             | Entity Reference | Target Project |


- **clearTeamsAndAssignments**: Thee default behavior for Project for the Web, and will remove all assignments and team members.
- **removeNamedResource** The default behavior for Project Operations, and will revert assignments to generic resources.

For more defaults on actions, see [Use Web API actions](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/use-web-api-actions)

## Specify fields to copy 
When the action is called, **Copy Project** will look at the project view **Copy Project Columns** to determine which fields to copy when the project is copied.
