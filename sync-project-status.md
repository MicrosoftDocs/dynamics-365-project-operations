---
title: Sync Project Status to prevent entry against closed projects
description: This article explains how to sync Project Status to prevent entry against inactive or closed projects.
author: ryansandnessMSFT
ms.date: 08/09/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandnessMSFT
---

# Sync Project Status to prevent entry against closed projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

## Scenario

Contoso is live with Microsoft Dynamics 365 Project Operations for resource/non-stocked scenarios. As part of normal business activities, projects may be completed or put on hold. To ensure no expenses or invoices are generated you can inactivate the project.

## Solution

### Prerequisites

-   Dynamics 365 Finance 10.0.29 or later must be installed.

-   Dual Write map 1.0.0.3 for Projects V2 (msdyn\_projects) must be installed or manually configured as described below.

## Create an updated version of the Project Operations integration Projects V2 dual-write map

Update the Project Operations Projects V2 dual-write map

1.  Navigate to the Data management  workspace and select Dual-write
2.  Select the **Project V2** (**msdyn\_projects**) dual-write map.
3.  Stop the map
4.  Open the map and click on **column** for PROJECTSTAGE \[PROJECTSTAGE\]
5.  Type a filter value of state to filter the list
6.  Choose the value **statecode \[Project Status\]** and click Ok.
7.  Select the map type column to edit the transform.
8.  Set **transform value** to **valuemap**.
9.  Add value mapping for **InProcess** to **0**
10. Add value mapping for **completed** to 1

![Screenshot showing Dual-write mapping](media/projectstage-dw-mapping.png)

11. Click Save
12. Click Save As
13. Set the **Publisher** field
14. Set the **Version** field to 1.0.0.3
15. Set the **Publisher** field to **Default publisher**.
16. Select Save.
17. Start the map

## Close a newly completed project

Dynamics 365 finance and operations uses the **project stage** field to differentiate between projects **in process** or **finished**. **Finished** projects cannot incur expenses or be invoiced to customers.

1. Select a project in Dataverse to inactivate
2. Navigate to an existing project in Dataverse

3. Click **Deactivate** in the ribbon
Note: You can select either the inactive or closed option as they will both behave the same in the context of finance and operations.

4.  In finance and operations open the All projects list page

5. Confirm the inactivated project does not appear in the list

6. In the **show projects** filter above the list change the value from **Active** to **All**.

7.  You will now see the inactivated project

If you attempt to log time or expense against this project in finance and operations you should not see the project for selection. If you manually enter the project number on an expense you will see a message like "Project stage finished does not allow recording in the project". Invoicing and other billing functions should be disabled as they will be in the context of a closed project.

