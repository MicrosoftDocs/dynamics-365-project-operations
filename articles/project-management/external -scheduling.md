---
# required metadata
title: Scheduling modes
description: This article provides information about external scheduling. 
author: ruhercul
ms.date: 10/07/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Scheduling modes

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Overview

The external scheduling mode enables customers to natively create, update and delete work breakdown structure related entities with limited validation and without the current limits enforced by Project for the Web. This project mode should only be used by customers who have the tools to define the work breakdown structure outside the scheduling logic provided by Project Operations or customers who need to store a very simple list of tasks and therefore do not required any scheduling logic. It is important to note that if the data is not correctly populated in the work breakdown structure related entities, it may not be rendered in the other grids used by Project Operations such as the resource reconciliation grid, the estimates grid, the tracking grid or the resource assignment grid.

## Settings

To use the external scheduling mode, customers must first create a new project and select the mode **Externally Scheduled** from the drop down on the project main form. Once this mode has been set on a project, it cannot be changed.

## Viewing the Work Breakdown Structure

When a project has enabled external scheduling, access to Project for the Web is restricted on that project. For a customer to view the work breakdown structure (WBS) they will need to navigate to the tracking tab where the full work breakdown structure will be displayed.

## Creating and editing the Work Breakdown Structure

When a project has enabled external scheduling, it is incumbent upon the customer to define the data for all work breakdown structure (WBS) related entities including tasks, team members, resource assignments and dependencies.

![](../media/projectplanningdatamodel.png)

## Validations

When accessing the tracking grid, the following validations remain in place and are enforced regardless of project mode:

- Need DEVS input

## Functional Limitations

the following operations are not permitted until a project has been converted:

### Project Planning

- **Copy project:** This operation is not supported on externally scheduled projects.
- **Move project:** Changing the start date of a project will not move the start of tasks or resource assignments in the work breakdown structure (WBS).
- **Updating the Project Manager:** Changing the project manager on the project main form will not automatically create a new project team member until the project has been converted.
- **Updating the project's work hour template:** Changing the project's work hour template will not recalculate the project's schedule.
- **Resource Assignment Contours:** Creating resource assignments will not automatically update mdyn\_PlannedWork, the field used to store resource assignment effort contours. Customers must define valid resource assignment contours if they display time phased effort in the resource assignment grid or the resource reconciliation grid. This contour must also be correctly formatted to trigger the calculation of both cost and sales price contours. It is recommended that customers create a project scheduled by Project for the Web and then review the associated data to confirm the requirements and formatting.

### Resource Management

- **Generic resource fulfillment:** Generic resource fulfillment will not be supported on externally scheduled projects. Attempts to fulfill active open requirements will create new project team members but will not
- **Delete Team Member:** Delete team member will not automatically delete resource assignments.

### Quoting and Contracting

- **Importing Quote Line and Contract Line details** : When importing quote or contract line details from a project, the application has only been tested to support a maximum of 500 tasks in the work breakdown structure based on a limit of 20 assignments per task.
- **Task based billing** :

### Time and Expense

- **Importing Time entries for assignments** :

### Actuals and Invoicing

While there are no changes to existing validations between the WBS and financial transactions, it is important to note that a customer should conform to the out of the box data model to ensure all downstream transactions execute as expected.
