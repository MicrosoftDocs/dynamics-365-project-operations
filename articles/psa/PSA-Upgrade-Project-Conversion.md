---
title: Feature changes from Project Service Automation to Project Operations
description: This article provides an overview of the feature changes from Project Service Automation to Dynamics 365 Project Operations.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 02/03/2022
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
ms.reviewer: johnmichalak
---

# Overview
Once a project has been successfully upgraded from Project Service Automation (PSA) 3.X to Project Operations Lite, all project work breakdown structures editable task grid will not be available. Customers will have the ability to review the work breakdown structure (WBS) in the tracking grid where new fields have been added to provide all details related to the task. For projects where edits to the WBS are required, customers will be able to selectively convert eligible projects to be editable in Project for the Web.

# Conversion Process

To convert a project a user must:

1.  Navigate to the project’s main form and select **Convert** from the ribbon.
2.  Select **OK** on the confirmation dialog to start the project conversion**.**
    1.  A banner will be displayed on the project’s main form indicating “*The project schedule is being converted. You cannot make changes to the project until the conversion is complete.”*
    2.  The user will be redirected to the project list.
3.  Once the project conversion has been completed:
    1.  The assigned project manager will receive an in-app notification on the right side of the application
    2.  The banner indicating conversion in projects will be removed.
    3.  The schedule tab will the new scheduling experience with Project for the Web. Any user with the appropriate licenses and security roles will be able to edit the work breakdown structure.
    4.  The scheduling engine field will be updated to Project for the Web.
    5.  The conversion ribbon action will be removed.

**Please note**: bulk conversion of projects is not permitted and any attempts to update a large volume of projects at the same time will be throttled. These guardrails are in place to ensure high performance for all customers.

# Manual vs Automatic Tasks

When an environment is upgraded from Project Service Automation to Project Operations, all tasks in the work breakdown structure are considered automatically scheduled. The concept of manually scheduled tasks is not available in Project for the Web. However, customers will have the option to define the preferred scheduling behavior of their projects using the [scheduling mode](https://learn.microsoft.com/en-us/dynamics365/project-operations/project-management/scheduling-modes) setting when creating new projects.

# Restricted Operations for pre-conversion projects

This section outlines the functional differences expected when projects have not been converted.

### Copy project

The copy Operation is only supported on converted projects. Upgraded projects cannot be converted prior to conversion.

### Move Project

Changing the start date of a project will not proportionately move the start of the tasks unless the project has been converted.

# Frequently asked questions

### What are the differences between converted projects and new project created after upgrade has been completed?

Projects converted after the environment has been upgraded will have a flag set on the projects setting the schedule to only respect the project calendar which is the behavior in project service automation. However, new projects created post upgrade will not have this flag set and as such will respect the working hours of a resource when they are assigned to a task.

### What do I do if my project fails to convert?

if your project fails to convert the first step will be to review the error logs to identify any common issues related to your work breakdown structure. if the logs do not identify a specific error that is actionable by the user then please contact customer support where your case can be reviewed further.

### How are business closures handled in project for the web?

project for the web does not respect enterprise defined business closures defined at the organization level, but it will respect other types of days off defined in a given work hour template.

### What are the limitations of Project for the Web?

[Create a work breakdown structure: Project Limitations](https://learn.microsoft.com/en-us/dynamics365/project-operations/project-management/create-wbs#project-limitations)

### Can I expect changes to my cost and sales estimates?

In the rare cases where resource assignment contours are recalculated or fall on a different date boundary than the source project there is a possibility that differences in sales and cost estimates could be observed. As part of the upgrade process, it is expected that customers test a representative sample set of projects to understand any potential schedule changes.
