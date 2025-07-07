---
title: Plan your work in Microsoft Project with the Project Operations add-in
description: This article describes how to use the Microsoft Project add-in for Microsoft Dynamics 365 Project Operations.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - bap-template
  - evergreen
ms.date: 07/07/2025
ms.topic: how-to
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Plan your work in Microsoft Project with the Project Operations add-in

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [banner](../includes/psa-now-project-operations.md)]

Microsoft Dynamics 365 Project Operations makes it easier to do project planning, including estimates. You can define the work so that costs, effort, and sales values are clear as the final proposal is submitted.

You can install the Microsoft Project desktop add-in for Project Operations and do your planning work in the familiar Microsoft Project environment. Use the robust planning and management capabilities of Microsoft Project, and then update your project plan in Project Operations.

> [!IMPORTANT]
> - The add-in is available only for customers who are upgrading from Project Service Automation to Project Operations and have projects that are currently outside the supported limits of Project for the Web.
> - Usage of this add-in will only be available for a limited time as we work to increase the limits of Project for the Web to meet all our customers' needs.
> - The add-in can't be used to edit projects that are created by using Project for the Web.
> - Before you can use SharePoint document management to store your Microsoft Project files for Project Operations projects, your Microsoft Project admin must turn on document management. 
> - The Microsoft Project desktop add-in for Project Operations is compatible only with Microsoft Project 2016 Professional Edition or later.


## Download and install the add-in

Have your Project Operations sign-in information ready. You need this information to connect from Microsoft Project to Project Operations.

To download and install the Microsoft Project desktop add-in for Project Operations, follow these steps.

1. From the Download Center, download the add-in for your supported version of Project Operations [version 4.88 and later](https://www.microsoft.com/download/details.aspx?id=105733).
1. Select the download link.
1. When the download is completed, select **Yes** to install the add-in.

## Configure the add-in

To configure the Microsoft Project desktop add-in for Project Operations, follow these steps.

1. Open Microsoft Project.
1. On the **Project Operations** tab, select **Connect**.
1. Enter your sign-in information, and then select **Sign in**.

You can now start to use the add-in.

## Assign Project Operations roles to project resources

To assign Project Operations roles to the project resources, follow these steps.

1. Open a project, and select the **Task** ribbon.
1. Select the **Gantt Chart** menu, and then select **Resource Sheet**.
1. On the resource sheet, select the **Project Operations Resource Role** dropdown menu, and then select a Project Operations role.

## Staff your project with resources

To staff your project with resources, follow these steps.

1. On the **Project Operations** tab, select a row, and then select **Find Resources**.
1. On the **Book Resource** page, select the resource to use for the project.
1. Select **Book**, and then select **OK**.

## Publish your project

When your project planning is completed, the next step is to import and publish the project in Project Operations.

The project is imported into Project Operations. The pricing and team generation processes are applied. Open the project in Project Operations to confirm that the team, project estimates, and work breakdown structure have been generated. The following table shows where to find the results.

| Microsoft Project | Project Operations |
|-------------------|--------------------|
| Gantt Chart | Imported into the **Work Breakdown Structure** page. |
| Resource Sheet | Imported into the **Project Team Members** page. |
| Use Usage | Imported into the **Project Estimates** page. |

### Import and publish your project

To import and publish your project, follow these steps.

1. On the **Project Operations** tab, go to **Publish** \> **New Project Operations Project**.
1. In the **Publish to a new project in Project Operations** dialog box, enter the project name, and select the customer.
1. Optional: Select **Link project plan to Project Operations** to link the plan's Project file to Project Operations.
1. Select **Publish**.

    By linking the Project file to Project Operations, you make the Project file the master and set the work breakdown structure in Project Operations to read-only. To change the project plan, you must make your changes in Microsoft Project and then publish them as updates to Project Operations.

## Edit a project that has been imported

To make changes to a project plan that has been imported into Project Operations, you have two options:

- Open the master file, and edit it in Microsoft Project.
- Unlink the file, and edit it directly in Project Operations. By default, a project that has been uploaded from Microsoft Project is locked and can be edited only in Microsoft Project. To edit the file in Project Operations, you must unlink it.

### Edit in Microsoft Project

To edit in Microsoft Project, follow these steps.

1. On the main menu, go to **Project Operations** \> **Projects**.
1. From the list of projects, open the project that you created in Microsoft Project.
1. On the ribbon, select **Open in MS Project**. The linked master file is opened in Microsoft Project.

### Unlink a file and edit in Microsoft Project Service

To unlink a file and edit it in Microsoft Project Service, follow these steps.


1. On the main menu, go to **Project Operations** \> **Projects**.
1. From the list of projects, open the project that you created in Microsoft Project.
1. On the ribbon, select **Unlink from MS Project**.

## Upload a Project file to SharePoint or Office Groups

You can upload your Project file to SharePoint and then find it under the associated documents for your Project Operations project. You must have your administrator configure SharePoint document management and turn it on for the Project entity.

You can also upload your Project file to [!INCLUDE[pn_onedrive_for_business](../includes/pn-onedrive-for-business.md)], if you have Office Groups set up.

### Upload a file for SharePoint

To upload a file for SharePoint, follow these steps.

1. On the main menu, go to **Project Operations** \> **Upload**.
1. Select **To Project Operations Project Documents**.
1. In the **Enable Open in Microsoft Project** dialog box, select **Yes** or **No**.

    - If you select **Yes**, you can select **Open in Microsoft Project** in Project Operations, open Microsoft Project, and load the Project file from the SharePoint document library.
    - If you select **No**, the **Open in Microsoft Project** link doesn't work.

1. In Project Operations, you can find the Project file under **Documents** for the specific Project Operations project.

### Upload a file for Office Groups

To upload a file for Office Groups, follow these steps.

1. On the main menu, go to **Project Operations** \> **Upload**.
1. Select **To Project Operations Project Documents**.
1. In the **Enable Open in Microsoft Project** dialog box, select **Yes** or **No**.

    - If you select **Yes**, you can select the **Open in Microsoft Project** link in Project Operations, open Microsoft Project, and load the Project file from the SharePoint document library.
    - If you select **No**, the **Open in Microsoft Project** link doesn't work.

1. In Project Operations, you can find the Project file under **Documents** for the specific Project Operations project.

## Read a resource loaded schedule

When a project is read from Project Operations, the resource's calendar isn't synchronized to the desktop client. If there are differences in the task durations, effort, or end, the resources and the desktop client probably don't have the same work hour template calendar applied to the project. Projects that are managed by Project for the Web aren't shown in the project lookup.

## Data synchronization

The tables in this section provide information about the synchronization of entity data between Project Operations and the Microsoft Project desktop add-in.

### Project Task entity

The following table outlines how Project Task entity data is synchronized between Project Operations and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Operations | Project Operations to Microsoft Project |
|---|---|---|---|
| Project Task | Due Date | Synchronized | Not synchronized |
| Project Task | Estimated Effort | Synchronized | Not synchronized |
| Project Task | MS Project Client ID | Synchronized | Not synchronized |
| Project Task | Parent Task | Synchronized | Not synchronized |
| Project Task | Project | Synchronized | Not synchronized |
| Project Task | Project task | Synchronized | Not synchronized |
| Project Task | Project Task Name | Synchronized | Not synchronized |
| Project Task | Resourcing unit (Deprecated in version 3.0) | Synchronized | Not synchronized |
| Project Task | Scheduled Duration | Synchronized | Not synchronized |
| Project Task | Start Date | Synchronized | Not synchronized |
| Project Task | WBS ID | Synchronized | Not synchronized |


### Team Member entity

The following table outlines how Team Member entity data is synchronized between Project Operations and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Operations | Project Operations to Microsoft Project |
|---|---|---|---|
| Team Member | MS Project Client ID | Synchronized | Not synchronized |
| Team Member | Position Name | Synchronized | Not synchronized |
| Team Member | project | Synchronized | Synchronized |
| Team Member | Project Team | Synchronized | Synchronized |
| Team Member | Resourcing Unit | Not synchronized | Synchronized |
| Team Member | Role | Not synchronized | Synchronized |
| Team Member | Working Hours | Not synchronized | Not synchronized |


### Resource Assignment entity


The following table outlines how Resource Assignment entity data is synchronized between Project Operations and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Operations | Project Operations to Microsoft Project |
|---|---|---|---|
| Resource Assignment | From Date | Synchronized | Not synchronized |
| Resource Assignment | Hours | Synchronized | Not synchronized |
| Resource Assignment | MS Project Client ID | Synchronized | Not synchronized |
| Resource Assignment | Planned Work | Synchronized | Not synchronized |
| Resource Assignment | Project | Synchronized | Not synchronized |
| Resource Assignment | Project Team | Synchronized | Not synchronized |
| Resource Assignment | Resource Assignment | Synchronized | Not synchronized |
| Resource Assignment | Task | Synchronized | Not synchronized |
| Resource Assignment | To Date | Synchronized | Not synchronized |


### Project Task Dependencies entity


The following table outlines how Project Task Dependencies entity data is synchronized between Project Operations and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Operations | Project Operations to Microsoft Project |
|---|---|---|---|
| Project Task Dependencies | Project Task Dependency | Synchronized | Not synchronized |
| Project Task Dependencies | Link Type | Synchronized | Not synchronized |
| Project Task Dependencies | Predecessor Task | Synchronized | Not synchronized |
| Project Task Dependencies | Project | Synchronized | Not synchronized |
| Project Task Dependencies | Successor Task | Synchronized | Not synchronized |

### Additional resources

[Project Manager Guide](../psa/project-manager-guide.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
