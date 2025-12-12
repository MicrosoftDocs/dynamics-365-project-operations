---
title: Plan your work in Microsoft Project with the Project Service Automation add-in
description: This article describes how to use the Microsoft Project add-in for Microsoft Dynamics 365 Project Service Automation.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - bap-template
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

# Plan your work in Microsoft Project with the Project Service Automation add-in

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3x](../includes/cc-applies-to-psa-app-3x.md)]

[!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes it easier to do project planning, including estimates. You can define the work so that costs, effort, and sales value are clear as the final proposal is submitted.

You can install the [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] and do your planning work in the familiar [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] environment. Use the robust planning and management capabilities of [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and then update your project plan in Project Service Automation.

> [!IMPORTANT]
> - Before you can use SharePoint document management to store your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] files for [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] projects, your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] admin must turn on document management.
> - The [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] is compatible only with [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] 2016 Professional Edition.

## Download and install the Project Service Automation add-in

Have your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] sign-in information ready. You need this information to connect from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

To download and install the Project Service Automation add-in, follow these steps.

1. From the Download Center, download the add-in for your supported version of Project Service, either [version 2.X](/dynamics365/project-operations/psa/overview#guidance-for-earlier-versions-app-version-2x-or-1x) or [version 3.4 and later](https://www.microsoft.com/download/details.aspx?id=57956).
1. Select the download link.
1. When the download is completed, select **Yes** to install the add-in.

## Configure the Project Service Automation add-in

To configure the Project Service Automation add-in, follow these steps.

1. Open [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].
1. On the **Project Service** tab, select **Connect**.
1. Enter your sign-in information, and then select **Sign in**.

You can now start to use the add-in.

## Read from a template

To start your project planning, read from a template that you created in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] and copied into [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Create a project template (Project Service Automation)](../psa/create-project-template.md)

To read from a template, follow these steps.

1. From the **Project Service** tab, select **Read** > **Project Service Automation Project Template**.
1. Select a project template in the list, and then select **Open**.

    > [!NOTE]
    > By default, the tasks that are copied from the template into Project are set as manually scheduled.

## Assign [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] roles to project resources

To assign Project Service roles to project resources, follow these steps.

1. Open a project, and select the **Task** ribbon.
1. Select the **Gantt Chart** menu, and then select **Resource Sheet**.
1. On the resource sheet, select the **Project Service Resource Role** dropdown menu, and then select a Project Service Automation role.

## Staff your project with resources

To staff your project with resources, follow these steps.

1. On the **Project Service** tab, select a row, and then select **Find Resources**.
1. On the **Book Resource** page, select the resource to use for the project.
1. Select **Book**, and then select **OK**.

## Publish your project

When your project planning is completed, the next step is to import and publish the project in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

The project is imported into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. The pricing and team generation processes are applied. Open the project in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to confirm that the team, project estimates, and work breakdown structure have been generated. The following table shows where to find the results.

| Microsoft Project | Project Service Automation |
|---|---|
| [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Gantt Chart** | Imported into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Work Breakdown Structure** page. |
| [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Resource Sheet** | Imported into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Team Members** page. |
| [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Use Usage** | Imported into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Estimates** page. |

### Import and publish your project

To import and publish your project, follow these steps.

1. On the **Project Service** tab, go to **Publish** \> **New Project Service Automation Project**.
1. In the **Publish to a new project in Project Service** dialog box, enter the project name, and select the customer.
1. Optional: Select **Link project plan to Project Service Automation** to link the plan's Project file to Project Service Automation.
1. Select **Publish**.

    By linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you make the Project file the master and set the work breakdown structure in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to read-only. To change the project plan, you must make your changes in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and then publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

## Edit a project that has been imported

To make changes to a project plan that has been imported into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you have two options:

- Open the master file, and edit it in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].
- Unlink the file, and edit it directly in Project Service. By default, a project that has been uploaded from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] is locked and can be edited only in Microsoft Project. To edit the file in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you must unlink it.

### Edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]

To edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], follow these steps.

1. On the main menu, go to **Project Service** \> **Projects**.
1. From the list of projects, open the project that you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].
1. On the ribbon, select **Open in MS Project**. The linked master file is opened in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].

### Unlink a file and edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] Service

To unlink a file and edit it in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] Service, follow these steps.

1. On the main menu, go to **Project Service** \> **Projects**.
1. From the list of projects, open the project that you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].
1. On the ribbon, select **Unlink from MS Project**.

## Upload a Project file to SharePoint or Office Groups

You can upload your Project file to SharePoint and then find it under the associated documents for your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project. You must have your administrator configure SharePoint document management and turn it on for the Project entity.

You can also upload your Project file to [!INCLUDE[pn_onedrive_for_business](../includes/pn-onedrive-for-business.md)], if you have Office Groups set up.

### Upload a file for SharePoint

To upload a file for SharePoint, follow these steps.

1. On the main menu, go to **Project Service** \> **Upload**.
1. Select **To Project Service Automation Project Documents**.
1. In the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog box, select **Yes** or **No**.

    - If you select **Yes**, you can select **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** in Project Service Automation, open [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.
    - If you select **No**, the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** link doesn't work.

4. In [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you can find the [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.

### Upload a file for Office Groups

To upload a file for Office Groups, follow these steps.

1. On the main menu, go to **Project Service** \> **Upload**.
1. Select **To Project Service Automation Project Documents**.
1. In the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog box, select **Yes** or **No**.

    - If you select **Yes**, you can select **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** in Project Service Automation, open [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.
    - If you select **No**, the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** link doesn't work.

1. In [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you can find the [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.

## Publish your project as a template

You can reuse your project by saving it as a project template in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. Project templates are reusable project plans in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. For more information, see [Create a project template (Project Service Automation)](../psa/create-project-template.md). 

To publish your project as a template, follow these steps.

1. On the **Project Service** tab, go to **Publish** \> **New Project Service Automation Project Template**.
1. In the **Publish to a new project in Project Service template** dialog box, enter the project template name.
1. Optional: Select **Link project plan to Project Service Automation** to link the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].
1. Select **Publish**.

By linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you make the Project file the master and set the work breakdown structure in the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] template to read-only. To change the project plan, you must make your changes in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and then publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

## Read a resource loaded schedule

When a project is read from Project Service Automation, the resource's calendar isn't synchronized to the desktop client. If there are differences in the task durations, effort, or end, the resources and the desktop client probably don't have the same work hour template calendar applied to the project.

## Data synchronization

The tables in this section provide information about the synchronization of entity data between Project Service Automation and the Microsoft Project desktop add-in.

### Project Task entity table

The following table outlines how Project Task entity data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Service Automation | Project Service Automation to Microsoft Project |
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

### Team Member entity table

The following table outlines how Team Member entity data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Service Automation | Project Service Automation to Microsoft Project |
|---|---|---|---|
| Team Member | MS Project Client ID | Synchronized | Not synchronized |
| Team Member | Position Name | Synchronized | Not synchronized |
| Team Member | project | Synchronized | Synchronized |
| Team Member | Project Team | Synchronized | Synchronized |
| Team Member | Resourcing Unit | Not synchronized | Synchronized |
| Team Member | Role | Not synchronized | Synchronized |
| Team Member | Working Hours | Not synchronized | Not synchronized |

### Resource Assignment entity table

The following table outlines how Resource Assignment entity data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Service Automation | Project Service Automation to Microsoft Project |
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

### Project Task Dependencies entity table

The following table outlines how Project Task Dependencies entity data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| Entity | Field | Microsoft Project to Project Service Automation | Project Service Automation to Microsoft Project |
|---|---|---|---|
| Project Task Dependencies | Project Task Dependency | Synchronized | Not synchronized |
| Project Task Dependencies | Link Type | Synchronized | Not synchronized |
| Project Task Dependencies | Predecessor Task | Synchronized | Not synchronized |
| Project Task Dependencies | Project | Synchronized | Not synchronized |
| Project Task Dependencies | Successor Task | Synchronized | Not synchronized |

### Additional resources

[Project Manager Guide](../psa/project-manager-guide.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
