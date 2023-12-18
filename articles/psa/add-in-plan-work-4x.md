---
title: Plan your work in Microsoft Project with the Project Service add-in
description: This article provides information about how to use the Microsoft Project add-in for Microsoft Project Service.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
ms.date: 12/07/2023
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Plan your work in Microsoft Project with the Project Service add-in

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3x](../includes/cc-applies-to-psa-app-3x.md)]

[!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes it easier for you to do your project planning, including estimates. You can define the work so that costs, effort, and sales value are clear as the final proposal is submitted.  

You can install the [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] and do your planning work in the familiar environment of [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]. Use the robust planning and management capabilities of [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and then update your project plan in Project Service Automation.  

> [!IMPORTANT]
> - The add-in is only available for existing Project Service Automation customers who either have active usage of the addin or have projects that are currently outside the supported limits of Project for the Web.
> - To use SharePoint document management to store your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] files for [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] projects, your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] admin will need to turn on document management. 
> - The [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] is only compatible with [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] 2016 Professional Edition.  

## Download and install the add-in  
 Have your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] sign-in information ready. You will need this information to connect from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

1.  From the Download Center, download the add-in for your supported version of Project Project Operations, either [V4.88+](https://www.microsoft.com/download/details.aspx?id=57956).  

2.  Select the download link.  

3.  When the download is complete, select **Yes** to install the add-in.  

## Configure the add-in  

1. Open [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and select the **Project Service** tab.  

2. Select **Connect**.  

3. Enter your sign-in information and then select **Sign in**.  

   Now you can start using the add-in.  

## Assign [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] roles to project resources  

1.  Open a project and select the **Task** ribbon.  

2. Select the **Gantt Chart** menu and then choose **Resource Sheet**.  

3. On the Resource Sheet, select the **Project Service Resource Role** drop-down menu and choose a Project Service Automation role.  

## Staff your project with resources  

1.  From the Project Service tab, select a row and select **Find Resources**.  

2.  On the **Book Resource** screen, select the resource that you want to use for the project.  

3.  Select **Book** and then select **OK**.  

## Publish your project  
When your project planning is complete, the next step is to import and publish the project in to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

The project will import into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. The pricing and team generation process are applied. Open the project in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to see that the team, project estimates, and work breakdown structure have been generated. The following table shows where to find the results.


|              Microsoft Project                                                           |                      Project Service Automation                                                                                   |
|------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Gantt Chart**   | Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Work Breakdown Structure** screen. |
| [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Resource Sheet** |   Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Team Members** screen.   |
|   [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Use Usage**    |    Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Estimates** screen.     |

**To import and publish your project**  
1. On the **Project Service** tab, go to **Publish** > **New Project Service Automation Project**.  

2. In the **Publish to a new project in Project Service** dialog box, enter the **Project Name** and select the **Customer**.  

3. Optionally, select **Link project plan to Project Service Automation** to link the plan Project file to Project Service Automation.  

4. Select **Publish**.  

   Linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes the Project file the master and sets the work breakdown structure in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to read-only.  In order to make changes to the project plan, you need to make them in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

## Edit a project that’s been imported  
 To make changes to a project plan that's been imported into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you have two options:  

- Open the master file and edit it in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

- Unlink the file and edit it directly in Project Service. By default, a project that’s been uploaded from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] is locked and can only be edited in Project. To edit the file in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], the file has to be unlinked.  

### Edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]  

1. On the main menu, go to **Project Service** > **Projects**.  

2. From the list of projects, open the one that you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

3. Select **Open in MS Project** from the ribbon. This will open the linked master file in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

### Unlink a file and edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] Service  

1. On the main menu, go to **Project Service** > **Projects**.  

2. From the list of projects, open the one that you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

3. Select **Unlink from MS Project** from the ribbon.  

## Upload a Project file to SharePoint or Office Groups  
 You can upload your Project file to SharePoint and find it under the Associated Documents for your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  You need to have your administrator configure SharePoint document management and turn it on for the Project entity. 

 You can also upload your Project file to [!INCLUDE[pn_onedrive_for_business](../includes/pn-onedrive-for-business.md)] if you have Office Groups set up.

### Upload a file for SharePoint  

1. On the main menu, go to **Project Service** > **Upload**.  

2. Select **To Project Service Automation Project Documents**.  

3. In the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog box, select **Yes** or **No**.  

   - If you select **Yes**, you'll be able select **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** in Project Service Automation, launch [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.  

   - If you select **No**, the link for **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** won't work.  

4. The [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file can be found in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  

### Upload a file for Office Groups  

1. On the main menu, go to **Project Service** > **Upload**.  

2. Select **To Project Service Automation Project Documents**.  

3. In the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog box, select **Yes** or **No**.  

   - If you select **Yes**, you'll be able to select **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** in Project Service Automation, launch [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.  

   - If you select **No**, the link for **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** won't work.  

4. The [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file can be found in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  

## Publish  your project as a template  
 You can save your project and reuse it by saving it as a project template in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. Project templates are reusable project plans in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. For more information, see [Create a project template (Project Service Automation)](../psa/create-project-template.md). 

1. On the **Project Service** tab, go to **Publish** > **New Project Service Automation Project Template**.  

2. In the **Publish to a new project in Project Service template** dialog box, enter the **Project template name**.  

3. Optionally, select **Link project plan to Project Service Automation** to link the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

4. Select **Publish**.  

Linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes the Project file the master and sets the work breakdown structure in the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] template to read-only.  In order to make changes to the project plan, you need to make them in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

## Read a resource loaded schedule

When reading a project from Project Service Automation, the resource's calendar isn't synchronized to the desktop client. If there are differences in the task durations, effort, or end, it's probably because the resources and the desktop client don't have the same work hour template calendar applied to the project.


## Data synchronization
The tables in this section provide information about the synchronization of entity data between Project Service Automation and the Microsoft Project desktop add-in.

### Project Task entity 
The following table outlines how Project Task entity data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Project Task | Due Date | Synchronized | Not synchronized |
| Project Task | Estimated Effort | Synchronized | Not synchronized |
| Project Task | MS Project Client ID | Synchronized | Not synchronized |
| Project Task | Parent Task | Synchronized | Not synchronized |
| Project Task | Project | Synchronized | Not synchronized |
| Project Task | Project task | Synchronized | Not synchronized |
| Project Task | Project Task Name | Synchronized | Not synchronized |
| Project Task | Resourcing unit (Deprecated in v3.0) | Synchronized | Not synchronized |
| Project Task | Scheduled Duration | Synchronized | Not synchronized |
| Project Task | Start Date | Synchronized | Not synchronized |
| Project Task | WBS ID | Synchronized | Not synchronized |

### Team Member entity 
The following table outlines how Team Member entity data is synchronized between Project Service Automation and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Team Member | MS Project Client ID | Synchronized | Not synchronized |
| Team Member | Position Name | Synchronized | Not synchronized |
| Team Member | project | Synchronized | Synchronized |
| Team Member | Project Team | Synchronized | Synchronized |
| Team Member | Resourcing Unit | Not synchronized | Synchronized |
| Team Member | Role | Not synchronized | Synchronized |
| Team Member | Working Hours | Not synchronized | Not synchronized |

### Resource Assignment entity 
The following table outlines how Resource Assignment entity data is synchronized between Project Service Automation and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
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
The following table outlines how Project Task Dependencies entity data is synchronized between Project Service Automation and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Project Task Dependencies | Project Task Dependency | Synchronized | Not synchronized |
| Project Task Dependencies | Link Type | Synchronized | Not synchronized |
| Project Task Dependencies | Predecessor Task | Synchronized | Not synchronized |
| Project Task Dependencies | Project | Synchronized | Not synchronized |
| Project Task Dependencies | Successor Task | Synchronized | Not synchronized |

### Additional resources
 [Project Manager Guide](../psa/project-manager-guide.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
