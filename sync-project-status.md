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

Contoso is live with Microsoft Dynamics 365 Project Operations for resource/non-stocked scenarios. As part of normal business activities, projects may be completed or put on hold. You can inactivate the project to ensure no expenses or invoices are generated.

## Solution

### Prerequisites

-   Microsoft Dynamics 365 Finance 10.0.29 or later must be installed.
-   Dual Write map 1.0.0.3 for Projects V2 (msdyn\_projects) must be installed or manually configured as described below.

## Create an updated version of the Project Operations integration Projects V2 dual-write map

To update the Project Operations Projects V2 dual-write map:

1. Go to the **Data management** workspace and select **Dual-write**.
2. Select the **Dual-write** tile.
3. from the T**Table map** column, locate and select **Project V2 (msdyn\_projects)**, and then select Stop.
4. Select the map name to open the map and then locate **PROJECTSTAGE \[PROJECTSTAGE\]**. You can type **state** in the filter value to narrow the list. 
5. Choose the value **statecode \[Project Status\]** and then select OK.
6.  Select **Add or edit transform** in the **map type** column to edit the transform.
7.  From **Transform type** select **valuemap**.
8.  Select **Add value mapping, and then type the following **Keys** and **Values**:

   Key       | Value 
   ----------|-------
   InProcess | 0     
   completed | 1     

![Screenshot showing Dual-write mapping](media/projectstage-dw-mapping.png)

9. Select **Save**.
10. Select **Save As**.
11. Set the **Publisher** field.
12. Set the **Version** field to 1.0.0.3.
14. Select **Save**.
15. Selec **Run** to start the map.
16. Select **Confirm** if asked to confirm prior to run. 

## Close a newly completed project

Dynamics 365 finance and operations uses the **project stage** field to differentiate between projects **in process** or **finished**. **Finished** projects can't incur expenses or be invoiced to customers.

1. Select a project in Dataverse to inactivate.
2. Navigate to an existing project in Dataverse.
3. Select **Deactivate** in the ribbon.

> [!NOTE]
> You can select either the **inactive** or the **closed** option as they will both behave the same in the context of finance and operations.

4. In finance and operations, open the **All projects list** page.
5. Confirm the inactivated project does not appear in the list.
6. In the **show projects** filter above the list change the value from **Active** to **All**.
7. You will now see the inactivated project.

If you attempt to log time or expense against this project in finance and operations you should not see the project for selection. If you manually enter the project number on an expense you will see a message like "Project stage finished does not allow recording in the project". Invoicing and other billing functions should be disabled as they will be in the context of a closed project.

