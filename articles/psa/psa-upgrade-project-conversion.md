---
title: Project Service Automation to Project Operations project scheduling conversion process
description: This article provides an overview of the feature changes for Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Project Operations.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: how-to
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Project Service Automation to Project Operations project scheduling conversion process

After a project has been successfully upgraded from Microsoft Dynamics 365 Project Service Automation 3.X to Dynamics 365 Project Operations  Core, editing project tasks in the task grid work breakdown structure (WBS) isn't possible. Customers are able to review the WBSs in the tracking grid where new fields have been added to provide all details that are related to the task. For projects where edits to the WBS are required, you can selectively convert eligible projects to the new Project for the web scheduling experience.

## Project conversion process

To convert a project, follow these steps:

1. Open the project's main page, and select **Convert** on the Action Pane.
1. In the confirmation message box, select **OK** to start the project conversion. The following actions occur:

    1. A message bar that appears on the project's main page states, "The project schedule is being converted. You can't make changes to the project until the conversion is complete."
    1. You're redirected to the project list.

    After the project conversion is completed, the following actions occur:

    1. The assigned project manager receives a notification on the right side of the application.
    1. The message bar that states that conversion is in progress is removed.
    1. The **Schedule** tab shows the new scheduling experience with Project for the web. Any user who has the appropriate licenses and security roles can edit the WBS.
    1. The **Scheduling engine** field is updated to **Project for the web**.
    1. The **Convert** button is removed from the Action Pane.

> [!IMPORTANT]
> Bulk conversion of projects isn't permitted. Any attempt to update a large volume of projects at the same time will be throttled. This limitation helps ensure high performance for all customers.

## Manual tasks vs. automatic tasks

When an environment is upgraded from Project Service Automation to Project Operations, all tasks in the WBS are considered automatically scheduled. The concept of manually scheduled tasks isn't available in Project for the web. However, you can define the preferred scheduling behavior for your projects by using the [scheduling mode](../project-management/scheduling-modes.md) setting when you create new projects.

## Restricted operations for preconversion projects

This section outlines the functional differences that you can expect when projects haven't been converted.

### Copy project

The **Copy** operation is supported only on converted projects. Upgraded projects can't be copied before conversion.

### Move project

A change to the start date of a project won't proportionately move the start of the tasks unless the project has been converted.

## Frequently asked questions

### What are the differences between converted projects and new projects that are created after the upgrade has been completed?

For projects that are converted after the environment has been upgraded, a flag is set that instructs the schedule to respect only the project calendar. This behavior matches the behavior in Project Service Automation. However, the flag won't be set for new projects that are created after the upgrade. Therefore, the schedule respects the working hours of resources when they're assigned to a task.

### What should I do if my project fails to be converted?

If your project fails to be converted, the first step is to review the error logs to identify any common issues that are related to your WBS. If the logs don't indicate a specific error that you can take action on, contact Customer Support so that your case can be reviewed further.

### How are business closures handled in Project for the web?

Project for the web doesn't respect business closures that the enterprise defines at the organization level. However, it respects other types of days off that are defined in a given work hour template.

### What are the limitations of Project for the web?

See the **Project limitations** section in [Create a work breakdown structure: Project Limitations](../project-management/create-wbs.md).

### Can I expect changes to my cost and sales estimates?

In rare cases where resource assignment contours are recalculated, or where they fall on a different date boundary than the source project, you might see differences in sales and cost estimates. As part of the upgrade process, customers are expected to test a representative sample set of projects, so that they can understand any potential schedule changes.
