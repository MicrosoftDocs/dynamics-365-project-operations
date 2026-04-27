---
title: Install and configure the Dynamics 365 expense management mobile app 
description: This article explains how to install and configure the Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 04/23/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
ms.custom: 
  - bap-template
---

# Install and configure the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how administrators can prepare your Microsoft Dynamics 365 Finance and Dataverse environments to support the Dynamics 365 expense management mobile app. For information on how to install the Dynamics 365 expense management mobile app on your mobile devices, see [Install and open the Dynamics 365 expense management mobile app on a mobile device](mobile-app-install-on-mobile-device.md).

> [!Note]
>  It is advisable to delete all components of the **Dynamics 365 expense management** mobile app from Dataverse if the Dynamics 365 Expense Management mobile app has already been installed during the public preview phase.
> There is no additional license required to use the Mobile app. Each user must be configured in **Dynamics 365 Finance** and minimum license requirement is **Teams user**.

## System requirements

To run the Dynamics 365 expense management mobile app with the latest improvements, you must use the following versions of Microsoft Dynamics 365 Finance with the latest quality update (QU) or later.
- 10.0.42 - 10.0.2095.147 or later
- 10.0.43 - 10.0.2177.72 or later
  
## Set up Dataverse for your Dynamics 365 Finance environment

Your Dynamics 365 Finance environment must be linked with a Dataverse environment, If Dataverse isn't already set up for your environment, follow the instructions in [Enable Power Platform Integration](/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration#enable-after-deploy).

When you create the Dataverse environment where you want to install the app, be sure to enable Dynamics 365 apps.

## Enable users in Dynamics 365 Finance

To enable users for Dynamics 365 expense management mobile app access, follow these steps in Dynamics 365 Finance.

1. In your Dynamics 365 Finance environment, go to **System administration** > **Users** > **Users**.
1. Select the **user**.
1. Select the **Person** field to default the **employee** association with the user. **Employee** should have **employment** in the **default legal entity** mapped with the user.
1. Assign the **Employee** role for the user.
1. Select **User Options** to open the user default settings. **Go to** the **Preferences tab**. **Set up** the Default **company** for the user.
   
## Enable Code components for canvas app
Once you enable the Dynamics 365 expense management mobile app in **Dynamics 365 Finance**, the next step is to activate the necessary code components for localization controls. This step is required to display the localized labels on the Dynamics 365 expense management mobile app and must be performed before installing the Dynamics 365 expense management mobile app. For more information, see [Enable the Power Apps component framework feature](https://github.com/MicrosoftDocs/powerapps-docs/blob/8bdb6cf00e2c10f73beafd70c2f694edc84f239a/powerapps-docs/developer/component-framework/component-framework-for-canvas-apps.md).

## Install the Dynamics 365 expense management mobile app in Dataverse

You must install the Dynamics 365 expense management mobile app in your Dataverse environment to enable users to access it when they sign in by using the Power Apps mobile app.

To install the Dynamics 365 expense management mobile app in your Dataverse environment, follow these steps:

1. Go to [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/home).
2. Select the desired environment in which you want to install the **Dynamics 365 Expense Management** mobile app.
3. Go to **Dynamics 365 Apps** within the **Resources** section.
4. Select **Install app** and install the **Dynamics 365 Expense Management** application.

## Refresh virtual entities in Dataverse
> [!Note]
>  This step is optional. Virtual entities in Dataverse are refreshed automatically as part of installation process. Only perform this step if you face data-related issues on the Mobile app screens.

Once the code components for canvas apps are enabled, the next crucial step is to enable the virtual entities used in the Dynamics 365 expense management mobile app. This action ensures that the canvas app can utilize the most up-to-date metadata of these virtual entities to enhance the overall functionality and user experience of the app. For more information, see [Refresh virtual entities](https://github.com/MicrosoftDocs/dynamics-365-unified-operations-public/blob/9ae4c7446f720f42f694048cd3561515569b7e98/articles/fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md#refresh-virtual-entity-metadata).

The following list shows the entities that need to be refreshed.

- mserp\_currencyentity
- mserp\_expensefieldsvisibilityentity
- mserp\_logisticsaddresscountryregionentity
- mserp\_logisticsaddresscountryregiontranslationentity
- mserp\_dimattributetrvtraveltxtentity
- mserp\_trvtravellocationentity
- mserp\_trvexpenseparametersentity
- mserp\_logisticsaddressstateentity
- mserp\_trvaddresszipcodeentity
- mserp\_trvexpmobilemasterdataentity
- mserp\_trvmileagerateentity
- mserp\_trvexpmobilereportapprovalentity
- mserp\_trvadmincustomfieldsentity
- mserp\_trvexpensecategoryentity
- mserp\_trvexpmobileactivitiesentity
- mserp\_trvexpmobileaddresscityentity
- mserp\_trvexpmobilecompanyinfoentity
- mserp\_trvexpmobiledocumententity
- mserp\_trvexpmobileexpenseentity
- mserp\_trvexpmobileexpensefieldvisibilityentity
- mserp\_trvexpmobileitemtaxentity
- mserp\_trvexpmobileprojentity
- mserp\_trvexpmobileprojlinepropertyentity
- mserp\_trvexpmobilereportentity
- mserp\_trvexpmobiletaxgroupentity
- mserp\_trvexpmobileexpenselineattachedtoreportentity
- mserp\_trvexpmobilereceiptattachedtoexpenselineentity
- mserp\_trvlogisticsaddresscountryregiontranslationentity
- mserp\_trvpaymethodentity
- mserp\_trvexpmobileattacheddocumententity
- mserp\_trvexpmobileunattacheddocumententity
  
## Grant access to the mobile app in Dataverse

After the mobile app solution is installed in your Dataverse environment, you must share it with your users. The Dynamics 365 expense management mobile app is a canvas app. To share it, follow the instructions in [Share a canvas app with your organization](/power-apps/maker/canvas-apps/share-app).

Each user must be assigned the Dynamics 365 **Teams member** license or higher license using the Microsoft Entra admin center.
Each relevant user must be assigned a **Basic user** and **Expense mobile user** security role in Dataverse that lets them create a connection for the custom connector. You can assign this role to a Dataverse group team. Then, any user who's a member of that team also has the role. Alternatively, you can assign the role directly to a user. 

- To assign a role to a group team, follow the instructions in [Manage the security roles of a team](/power-platform/admin/manage-group-teams#manage-the-security-roles-of-a-team). We recommend that you use group teams if you must assign the role to multiple users. For information about how to manage team members, see [Manage team members](/power-platform/admin/manage-teams#manage-team-members).
- To assign a role directly to a user, follow the instructions in [Assign a security role to a user](/power-platform/admin/assign-security-roles).



