---
title: Use the Project Service Add-in to plan your work in Microsoft Project | MicrosoftDocs
description: This article provides information about how to add, configure, and use the Microsoft Project add-in for Microsoft Project Service.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
ms.date: 04/06/2019
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Use the Project Service Automation Add-in to plan your work in Microsoft Project

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-1x-2x](../includes/cc-applies-to-psa-app-1x-2x.md)]

[!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes it easier for you to do your project planning, including estimates. You can define the work so that costs, effort, and sales value are clear as the final proposal is submitted.  

 Now you can install the [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] and do your planning work in the familiar environment of [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]. Use the robust planning and management capabilities of [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and then update your project plan in Project Service Automation.  

> [!IMPORTANT]
> - To use SharePoint document management to store your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] files for [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] projects, your [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] admin will need to turn on document management. 
> - The [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] is only compatible with [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] 2016 Professional Edition.
> - The [!INCLUDE[pn_ms_dyn_365_psa_for_ms_project](../includes/pn-ms-dyn-365-psa-for-ms-project.md)] is only compatible with Dynamics 365 Project Service. It is not compatible with Dynamics 365 Project Operations.

## Download and install the add-in  
 Have your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] sign-in information ready. You will need this information to connect from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

1.  From the Download Center, download the add-in for your supported version of Project Service, either [V2.X](/dynamics365/project-operations/psa/overview#guidance-for-earlier-versions-app-version-2x-or-1x) or [V3.4+](https://www.microsoft.com/download/details.aspx?id=57956).  

2.  Click the download link.  

3.  When the download is complete, click **Yes** to install the add-in.  

## Configure the add-in  

1. Open [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and click the **Project Service** tab.  

2. Click **Connect**.  

3. Enter your sign-in information and then click **Sign in**.  

   Now you can start using the add-in.  

## Read from a template  
 Read from a template that you created in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] and copied into [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] to start your project planning. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Create a project template (Project Service Automation)](../psa/create-project-template.md)  

1.  From the **Project Service** tab, click **Read** > **Project Service Automation Project Template**.  

2.  Choose a project template from the list and then click **Open**.  

    > [!NOTE]
    >  By default, the tasks that are copied from the template into Project are set as manually scheduled.  

## Assign [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] roles to project resources  

1.  Open a project and click the **Task** ribbon.  

2.  Click the **Gantt Chart** menu and then choose **Resource Sheet**.  

3.  On the Resource Sheet, click the **Project Service Resource Role** drop-down menu and choose a Project Service Automation role.  

## Staff your project with resources  

1.  From the Project Service tab, select a row and click **Find Resources**.  

2.  On the **Book Resource** screen, select the resource that you want to use for the project.  

3.  Click **Book** and then click **OK**.  

## Publish your project  
When your project planning is complete, the next step is to import and publish the project in to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

The project will import into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. The pricing and team generation process are applied. Open the project in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to see that the team, project estimates, and work breakdown structure have been generated. The following table shows where to find the results:

| Project | Details |
| ---- | --- |
|  [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Gantt Chart**   | Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Work Breakdown Structure** screen. |
| [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Resource Sheet** |   Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Team Members** screen.   |
|   [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] **Use Usage**    |    Imports into the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] **Project Estimates** screen.     |

**To import and publish your project**  
1. From the **Project Service** tab, click **Publish** > **New Project Service Automation Project**.  

2. On **Publish to a new project in Project Service** dialog box, enter the **Project Name** and select the **Customer**.  

3. Optionally check the **Link project plan to Project Service Automation** to link the plan Project file to Project Service Automation.  

4. Click **Publish**.  

   Linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes the Project file the master and sets the work breakdown structure in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] to read-only.  In order to make changes to the project plan, you need to make them in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

## Edit a project that’s been imported  
 To make changes to a project plan that's been imported into [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], you have two options:  

- Open the master file and edit it in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

- Unlink the file and edit it directly in Project Service. By default, a project that’s been uploaded from [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] is locked and can only be edited in Project. To edit the file in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)], the file has to be unlinked.  

### Edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]  

1. From the main menu, click **Project Service** > **Projects**.  

2. From the list of projects, open the one you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

3. Click **Open in MS Project** from the ribbon. This will open the linked master file in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

### Unlink a file and edit in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] Service  

1. From the main menu, click **Project Service** > **Projects**.  

2. From the list of projects, open the one you created in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)].  

3. Click **Unlink from MS Project** from the ribbon.  

## Upload a Project file to SharePoint or Office Groups  
 You can upload your Project file to SharePoint and find it under the Associated Documents for your [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  You need to have your administrator configure SharePoint document management and turn it on for the Project entity. 

 You can also upload your Project file to [!INCLUDE[pn_onedrive_for_business](../includes/pn-onedrive-for-business.md)] if you have Office Groups set up.

### Upload a file for SharePoint  

1. From the main menu, click **Project Service** > **Upload**.  

2. Select **To Project Service Automation Project Documents**.  

3. On the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog, select **Yes** or **No**.  

   - If you click **Yes**, you'll be able select the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** button in Project Service Automation, launch [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.  

   - If you click **No**, the link for the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** button won't work.  

4. The [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file can be found in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  

### Upload a file for Office Groups  

1. From the main menu, click **Project Service** > **Upload**.  

2. Select **To Project Service Automation Project Documents**.  

3. On the **Enable Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** dialog, select **Yes** or **No**.  

   - If you click **Yes**, you'll be able to select the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** button in Project Service Automation, launch [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)], and load the Project file from the SharePoint document library.  

   - If you click **No**, the link for the **Open in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)]** button won't work.  

4. The [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] file can be found in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] under **Documents** for the specific [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] project.  

## Publish  your project as a template  
 You can save your project and reuse it by saving it as a project template in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  Project templates are reusable project plans in [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)]. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Create a project template (Project Service Automation)](../psa/create-project-template.md)  

1. From the **Project Service** tab, click **Publish** > **New Project Service Automation Project Template**.  

2. On the **Publish to a new project in Project Service template** dialog box, enter the **Project template name**.  

3. Optionally, check the **Link project plan to Project Service Automation** to link the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].  

4. Click **Publish**.  

Linking the Project file to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] makes the Project file the master and sets the work breakdown structure in the [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)] template to read-only.  In order to make changes to the project plan, you need to make them in [!INCLUDE[pn_microsoft_project](../includes/pn-microsoft-project.md)] and publish them as updates to [!INCLUDE[pn_project_service_auto](../includes/pn-project-service-auto.md)].

## Read a resource loaded schedule

When reading a project from Project Service Automation, the resource's calendar isn't synchronized to the desktop client. If there are differences in the task durations, effort, or end, it's probably because the resources and the desktop client don't have the same work hour template calendar applied to the project.


## Data Synchronization

The following table outlines how data is synchronized between Project Service Automation and the Microsoft Project desktop add-in.

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Project Task | Due Date | ● | - |
| Project Task | Estimated Effort | ● | - |
| Project Task | MS Project Client ID | ● | - |
| Project Task | Parent Task | ● | - |
| Project Task | Project | ● | - |
| Project Task | Project task | ● | - |
| Project Task | Project Task Name | ● | - |
| Project Task | Resourcing unit (Deprecated in v3.0) | ● | - |
| Project Task | Scheduled Duration | ● | - |
| Project Task | Start Date | ● | - |
| Project Task | WBS ID | ● | - |

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Team Member | MS Project Client ID | ● | - |
| Team Member | Position Name | ● | - |
| Team Member | project | ● | ● |
| Team Member | Project Team | ● | ● |
| Team Member | Resourcing Unit | - | ● |
| Team Member | Role | - | ● |
| Team Member | Working Hours | Not synced | Not synced |

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Resource Assignment | From Date | ● | - |
| Resource Assignment | Hours | ● | - |
| Resource Assignment | MS Project Client ID | ● | - |
| Resource Assignment | Planned Work | ● | - |
| Resource Assignment | Project | ● | - |
| Resource Assignment | Project Team | ● | - |
| Resource Assignment | Resource Assignment | ● | - |
| Resource Assignment | Task | ● | - |
| Resource Assignment | To Date | ● | - |

| **Entity** | **Field** | **Microsoft Project to Project Service Automation** | **Project Service Automation to Microsoft Project** |
| --- | --- | --- | --- |
| Project Task Dependencies | Project Task Dependency | ● | - |
| Project Task Dependencies | Link Type | ● | - |
| Project Task Dependencies | Predecessor Task | ● | - |
| Project Task Dependencies | Project | ● | - |
| Project Task Dependencies | Successor Task | ● | - |

### See Also  
 [Project Manager Guide](../psa/project-manager-guide.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
