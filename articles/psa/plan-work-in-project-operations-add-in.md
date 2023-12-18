---
title: Plan your work in Microsoft Project with the Project Operations add-in
description: This article provides information about how to use the Microsoft Project add-in for Microsoft Project Operations.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
ms.date: 12/18/2023
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Plan your work in Microsoft Project with the Project Operations add-in

[!include [banner](../includes/psa-now-project-operations.md)]

Project Operations makes it easier for you to do your project planning, including estimates. You can define the work so that costs, effort, and sales value are clear as the final proposal is submitted.  

You can install the Microsoft Project desktop add-in for Project Operations and do your planning work in the familiar environment of Microsoft Project. Use the robust planning and management capabilities of Microsoft Project and then update your project plan in Project Operations.  

> [!IMPORTANT]
> - The add-in is only available for existing Project Operations customers who either have active usage of the add-in or have projects that are currently outside the supported limits of Project for the Web.
> - The add-in cannot be used to edit projects created using Project for the Web.
> - To use SharePoint document management to store your Microsoft Project files for Project Operations projects, your Microsoft Project admin will need to turn on document management. 
> - The Microsoft Project desktop add-in for Project Operation is only compatible with microsoft Project 2016 Professional Edition or newer.  

## Download and install the add-in  
Have your Project Operations sign-in information ready. You will need this information to connect from Microsoft Project to Project Operations.  

1.  From the Download Center, download the add-in for your supported version of Project Operations [V4.88+](https://www.microsoft.com/en-us/download/details.aspx?id=105733).  

2.  Select the download link.  

3.  When the download is complete, select **Yes** to install the add-in.  

## Configure the add-in  

1. Open Microsoft Project and select the **Project Operations** tab.  

2. Select **Connect**.  

3. Enter your sign-in information and then select **Sign in**.  

   Now you can start using the add-in.  

## Assign Project Operations roles to project resources  

1.  Open a project and select the **Task** ribbon.  

2. Select the **Gantt Chart** menu and then choose **Resource Sheet**.  

3. On the Resource Sheet, select the **Project Operations Resource Role** drop-down menu and choose a Project Operations role.  

## Staff your project with resources  

1.  From the Project Operations tab, select a row and select **Find Resources**.  

2.  On the **Book Resource** screen, select the resource that you want to use for the project.  

3.  Select **Book** and then select **OK**.  

## Publish your project  
When your project planning is complete, the next step is to import and publish the project in to Project Operations.  

The project will import into Project Operations. The pricing and team generation process are applied. Open the project in Project Operations to see that the team, project estimates, and work breakdown structure have been generated. The following table shows where to find the results.


|              Microsoft Project                                                           |                      Project Operations                                                                                   |
|------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **Gantt Chart**   | Imports into the **Work Breakdown Structure** screen. |
| **Resource Sheet** |   Imports into the **Project Team Members** screen.   |
| **Use Usage**    | Imports into the **Project Estimates** screen.     |

**To import and publish your project**  
1. On the **Project Operations** tab, go to **Publish** > **New Project Operations Project**.  

2. In the **Publish to a new project in Project Operations** dialog box, enter the **Project Name** and select the **Customer**.  

3. Optionally, select **Link project plan to Project Operations** to link the plan Project file to Project Operations.  

4. Select **Publish**.  

   Linking the Project file to Project Operations makes the Project file the master and sets the work breakdown structure in Project Operations to read-only.  In order to make changes to the project plan, you need to make them in Microsoft Project and publish them as updates to Project Operations.  

## Edit a project that’s been imported  
 To make changes to a project plan that's been imported into Project Operations, you have two options:  

- Open the master file and edit it in Microsoft Project.  

- Unlink the file and edit it directly in Project Operations. By default, a project that’s been uploaded from Microsoft Project is locked and can only be edited in Project. To edit the file in Project Operations, the file has to be unlinked.  

## Edit in Microsoft Project  

1. On the main menu, go to **Project Operations** > **Projects**.  

2. From the list of projects, open the one that you created in Microsoft Project.  

3. Select **Open in MS Project** from the ribbon. This will open the linked master file in Microsoft Project.  

### Unlink a file and edit in Microsoft Project Service  

1. On the main menu, go to **Project Operations** > **Projects**.  

2. From the list of projects, open the one that you created in Microsoft Project.  

3. Select **Unlink from MS Project** from the ribbon.  

## Upload a Project file to SharePoint or Office Groups  
 You can upload your Project file to SharePoint and find it under the Associated Documents for your Project Operations project.  You need to have your administrator configure SharePoint document management and turn it on for the Project entity. 

 You can also upload your Project file to [!INCLUDE[pn_onedrive_for_business](../includes/pn-onedrive-for-business.md)] if you have Office Groups set up.

## Upload a file for SharePoint  

1. On the main menu, go to **Project Operations** > **Upload**.  

2. Select **To Project Operations Project Documents**.  

3. In the **Enable Open in Microsoft Project** dialog box, select **Yes** or **No**.  

   - If you select **Yes**, you'll be able select **Open in Microsoft Project** in Project Operations, launch Microsoft Project, and load the Project file from the SharePoint document library.  

   - If you select **No**, the link for **Open in Microsoft Project** won't work.  

4. The Microsoft Project file can be found in Project Operations under **Documents** for the specific Project Operations project.  

## Upload a file for Office Groups  

1. On the main menu, go to **Project Operations** > **Upload**.  

2. Select **To Project Operations Project Documents**.  

3. In the **Enable Open in Microsoft Project** dialog box, select **Yes** or **No**.  

   - If you select **Yes**, you'll be able to select **Open in Microsoft Project** in Project Operations, launch Microsoft Project, and load the Project file from the SharePoint document library.  

   - If you select **No**, the link for **Open in Microsoft Project** won't work.  

4. The Microsoft Project file can be found in Project Operations under **Documents** for the specific Project Operations project.  


## Read a resource loaded schedule

When reading a project from Project Operations, the resource's calendar isn't synchronized to the desktop client. If there are differences in the task durations, effort, or end, it's probably because the resources and the desktop client don't have the same work hour template calendar applied to the project.  Project managed by Project for the Web will not be displayed in the project lookup.


## Data synchronization
The tables in this section provide information about the synchronization of entity data between Project Operations and the Microsoft Project desktop add-in.

### Project Task entity 
The following table outlines how Project Task entity data is synchronized between Project Operations and the Microsoft Project desktop add-in.

| **Entity** | **Field** | **Microsoft Project to Project Operations** | **Project Operations to Microsoft Project** |
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
The following table outlines how Team Member entity data is synchronized between Project Operations and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Operations** | **Project Operations to Microsoft Project** |
| --- | --- | --- | --- |
| Team Member | MS Project Client ID | Synchronized | Not synchronized |
| Team Member | Position Name | Synchronized | Not synchronized |
| Team Member | project | Synchronized | Synchronized |
| Team Member | Project Team | Synchronized | Synchronized |
| Team Member | Resourcing Unit | Not synchronized | Synchronized |
| Team Member | Role | Not synchronized | Synchronized |
| Team Member | Working Hours | Not synchronized | Not synchronized |

### Resource Assignment entity 
The following table outlines how Resource Assignment entity data is synchronized between Project Operations and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Operations** | **Project Operations to Microsoft Project** |
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
The following table outlines how Project Task Dependencies entity data is synchronized between Project Operations and the Micros

| **Entity** | **Field** | **Microsoft Project to Project Operations** | **Project Operations to Microsoft Project** |
| --- | --- | --- | --- |
| Project Task Dependencies | Project Task Dependency | Synchronized | Not synchronized |
| Project Task Dependencies | Link Type | Synchronized | Not synchronized |
| Project Task Dependencies | Predecessor Task | Synchronized | Not synchronized |
| Project Task Dependencies | Project | Synchronized | Not synchronized |
| Project Task Dependencies | Successor Task | Synchronized | Not synchronized |

### Additional resources
 [Project Manager Guide](../psa/project-manager-guide.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
