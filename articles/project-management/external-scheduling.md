---
# required metadata
title: External scheduling
description: This article provides information about external scheduling. 
author: ruhercul
ms.date: 10/31/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# External scheduling

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Overview

The external scheduling mode enables you to natively create, update, and delete work breakdown structure related entities with limited validation and without the current limits enforced by Microsoft Project for the Web. This mode should only be used by customers who have the tools to define a work breakdown structure outside the scheduling logic provided by Project Operations, or by customers who do need to manage schedule hierarchy, dependencies, or task duration. It's important to note that if the data isn't correctly populated in the work breakdown structure related entities, it may not be rendered in the resource reconciliation grid, estimates grid, tracking grid, or the resource assignment grid.

## Configuration
This feature is enabled by default. However, on the out of the box project main form, the field isn't visible by default. To enable the field, navigate to the main form of the project entity in the Maker portal, select the **Scheduling Engine** field, and then change the field to **Visible by Default**.  If you do not use the out of the box project main form, edit your existing form, and add the **Scheduling Engine** field.  

## Settings

To use the external scheduling mode, you must first create a new project, and then select the scheduling engine **Externally Scheduled** from the drop down on the project main form. Once this mode has been set up on a project, it can't be changed.

## Viewing the Work Breakdown Structure

When a project is externally scheduled, access to Project for the Web is restricted on that project. To view the work breakdown structure (WBS) you need to navigate to the tracking grid where the full work breakdown structure is displayed, 

## Creating and editing the Work Breakdown Structure

When a project has enabled external scheduling, it's necessary for you to define the data for all work breakdown structure (WBS) related entities including tasks, team members, resource assignments and dependencies.

![Diagram of the project planning data model](media/projectplanningdatamodel.png)

## Functional Limitations

The following operations aren't permitted on an externally scheduled project:

### Project Planning

- **Copy project:** This operation isn't supported on externally scheduled projects.
- **Move project:** Changing the start date of a project won't move the start of tasks or resource assignments in the work breakdown structure (WBS).
- **Updating the Project Manager:** Changing the project manager on the project main form won't automatically create a new project team member until the project has been converted.
- **Updating the project's work hour template:** Changing the project's work hour template won't recalculate the project's schedule.
- **Resource Assignment Contours:** Creating resource assignments won't automatically update mdyn\_PlannedWork, the field used to store resource assignment effort contours. You must define valid resource assignment contours if you display time-phased effort in the resource assignment grid or in the resource reconciliation grid. This contour must be correctly formatted to trigger the calculation of both cost and sales price contours. It's recommended that you create a test project scheduled by Project for the Web, and then review the associated data to confirm the requirements and formatting.

### Resource Management

- **Generic resource fulfillment:** Generic resource fulfillment won't be supported on externally scheduled projects. Attempts to fulfill active open requirements will create new project team members but won't delete the generic team member or replace them on any existing resource assignments.

- **Delete Team Member:** Delete team member won't automatically delete resource assignments.

### Quoting and Contracting

- **Importing Quote Line and Contract Line details** : When importing quote or contract line details from a project, the application has only been tested to support a maximum of 500 tasks in the work breakdown structure based on a limit of 20 assignments per task.

### Actuals and Invoicing

- While there are no changes to existing validations between the WBS and financial transactions, it's important to note that you should conform to the out of the box data model to ensure all downstream transactions execute as expected.
