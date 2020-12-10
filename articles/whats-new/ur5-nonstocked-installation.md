---
title: Update Project Operations in your Finance environment
description: This topic provides information about how to update Project Operations in your Dynamics 365 Finance environment.
author: ruhercul
manager: tfehr
ms.date: 12/10/2020
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: ruhercul
---

# Update Project Operations in your Finance environment

_**Applies To:** Project Operations for resource/non-stocked based scenarios_


There are three procedures that are required to update Dynamics 365 Project Operations to Update 5(UR5):

1. [Import the package into your preview project](#import).
2. [Apply the update](#apply).
3. [Update your Dataverse environment](#update).

## <a name="import"></a>Import the package into your preview project

1. Sign in to [Lifecycle Services (LCS)](https://lcs.dynamics.com/) as a Project Owner or Environment manager.
2. From the list of projects, select your LCS project.
3. On the **Project** page, in the **Enviornments** group, open the environment tp update.
4. Verify that the environment is running. If it isn't started, start the environment.
5. In the **New release** section under **Availalble updates**, select **View update** for 10.0.15.

![View update button](media/view-update.png)

6. On the **Binary updates** page, select **Save package**.
7. On the **Review and save updates** page, select **Save package**.
8. On the **Save package to asset library** pane that opens, enter the package name and then select **Save package**.
9. When LCS has finished saving the package, the **Done** button is enabled. Select **Done**. LCS will verify the package. Verification can take a few minutes or up to one hour.


## <a name="apply"></a>Apply the package update

1. In LCS, on the **Environment details** page, select **Maintain** > **Apply Updates**
2. Select the package you saved earlier from the list, and then select **Apply**.
3. Select **Yes** on the dialog box to confirm that you want to deploy the package.

![Confirm package deployment dialog box](media/confirm-package-deployment.png)

4. Select **Yes** on the dialog box to confirm that you want to update the application.

![Confirm application update dialog box](media/confirm-application-update.png)

The deployment and application update will start. 

On the **Environment details** page, in the top right corner, the environment status will update to **Servicing**. In approximately two hours, the update will be complete. 
The application release information will update to **Microsoft Dynamics 365 for Finance and Operations 10.0.15)** and the environment status will update to **Deployed**.


## <a name="update"></a>Update your Dataverse environment

1. Log in to the [Power Platform admin center](https://admin.powerplatform.com/).
2. In the list, find and open the environment you used to install Project Operation.
3. On the **Environments** page, select **Resource** > **Dynamics 365 apps**.
4. In the list, locate **Microsft Dynamics 365 Project Operations**, and in the **Status** column, select **Update Available**.
5. Select the **I agree to the terms of service** check box, and then select **Update**. The latest version of the solution will be installed.

AFter the installation is complete, you will have version 4.5.0.134 installed.

## Configure new features

### Enable dual write mapping

After you complete the update on the Finance and Dataverse environments, you can enable the required dual write mappings. Complete the following procedures to enable dual write mappings.

1. [Update security settings on Customer Engagement environment](#security)
2. [Refresh data entities](#refresh)
3. [Update and run the dual write mappings](#run)

### <a name="security"></a>Update security settings on the Dataverse environment

The following updates to the security privileges for entities are required as part of the update to UR5.

1. In your Dataverse environment, go to **Settings**, and in the **System** group, select **Security**.

![Dataverse environment settings](media/Picture21.png)

2. Select **Security Roles**.
3. From the list of roles, select **dual-write app user** and select the **Custom Entities** tab. 
4. Verify that the role has **Read** and **Append To** permissions for:

      - **Currency Exchange Rate Type**
      - **Chart Of Accounts** 
      - **Fiscal Calendar** 
      - **Ledger**

5. After the security role is updated, go to **Settings** > **Security** > **Teams** and verify that the **dual-write app user** role has been applied to the team. 

### <a name="refresh"></a>Refresh data entities from the update

1. In your Finance environment, open the **Data management** workspace, and then open the **Framework parameters** page.
2. On the **Entity settings** tab, select **Refresh entity list**.
3. Select **Close** on the dialog box to confirm the entity refresh.

 > [!NOTE]
 > This process will take approximately 20 minutes to complete. You will be notified when the refresh is complete.

### <a name="run"></a>Update dual write mappings

1. In the **Data management** workspace, select **Dual write**.
2. Select **Apply solutions**, select both solutions in the list, and then select **Apply**.
3. On the **Dual-write** page, select the following table maps and then select **Stop**:

    - **Project Operations integration actuals (msdyn_actuals)**
    - **Project Operations integration entity for expense estimates (msdyn_estimatelines)**
    - **Project Operations integration actualsproject expenses export entity (msdyn_expenses)**

4. On the **Table map version** page, apply a new version of the map to each of the three entities.
5. On the **Dual-write** page, select run to restart the maps.
6. From the list of maps, select the **Ledger (msdyn_ledgers)** map with all prerequisites and select the **Initial sync** check box. 
7. In the **Master for initial sync** field, select **Finance and Operations apps** and then select **Run**.
 
 ![Ledger map synchronization](media/DW6.png)
 
