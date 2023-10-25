---
title: Install and configure the Expense mobile app 
description: This article explains how to install and configure the Expense mobile app.
author: mukumarm
ms.date: 10/25/2023
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
ms.custom: bap-template
---

# Install and configure the Expense mobile app

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

> [!IMPORTANT]
> The functionality that's described in this article is available as part of a preview release. The functionality and the content of this article are subject to change. For more information about preview releases, see [One version service updates FAQ](/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

This article explains how administrators can prepare your Microsoft Dynamics 365 Finance and Dataverse environments to support the Expense mobile app. For information on how to install the Expense mobile app on your mobile devices, see [Install and open the Expense mobile app on a mobile device](mobile-app-install-on-mobile-device.md).

## System requirements

To run the Expense mobile app, you must use the following versions of Microsoft Dynamics 365 Finance with the latest quality update (QU) or later.
- 10.0.37 - 10.0.1725.37 or later
  
## Set up Dataverse for your Dynamics 365 Finance environment

Your Dynamics 365 Finance environment must be linked with a Dataverse environment, If Dataverse isn't already set up for your environment, follow the instructions in [Enable Power Platform Integration](/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration#enable-after-deploy).

When you create the Dataverse environment where you want to install the app, be sure to enable Dynamics 365 apps.

## Enable the Expense mobile app in Dynamics 365 Finance

To enable the Expense mobile app in Dynamics 365 Finance, follow these steps.

1. In your Dynamics 365 Finance environment, go to **Workspaces** \> **Feature Management**.
1. In the list, find and select **feature Use expense mobile application for intuitive expense entry experience**, and then select **Enable now**.

## Enable users in Dynamics 365 Finance

To enable users for the Expense mobile app access, follow these steps in Dynamics 365 Finance.

1. In your Dynamics 365 Finance environment, go to **System administration** > **Users** > **Users**.
1. Select the **user**.
1. Select the **Person** field to default the **employee** association with the user. **Employee** should have **employment** in the **default legal entity** mapped with the user.
1. Assign the **Employee** role for the user.
1. Select **User Options** to open the user default settings. **Go to** the **Preferences tab**. **Set up** the Default **company** for the user.
   
## Enable Code components for canvas app
Once you enable the expense mobile app in **Dynamics 365 Finance**, the next step is to activate the necessary code components for localization controls. This step is required to display the localized labels on the Expense mobile app and must be performed before installing the Expense mobile app. For more information, see [Enable the Power Apps component framework feature](https://github.com/MicrosoftDocs/powerapps-docs/blob/8bdb6cf00e2c10f73beafd70c2f694edc84f239a/powerapps-docs/developer/component-framework/component-framework-for-canvas-apps.md)

## Install the Expense mobile app in Dataverse

You must install the Expense mobile app in your Dataverse environment to enable users to access it when they sign in by using the Power Apps mobile app.

To install the Expense mobile app in your Dataverse environment, follow these steps.

1. In AppSource, go to [Dynamics 365 Expense Mobile Application (Public Preview)](https://appsource.microsoft.com/product/dynamics-365/mscrm.msdyn_expense_mobile-preview?flightCodes=d365expensemobile&exp=ubp8).
1. Select **Get it now**.
1. Select the previously created or updated environment where you want to install the Expense mobile app, and then select **Install**.
1. After successful installation, **Dynamics 365 Expense Mobile** is listed as a solution on the **Solutions** tab in Power Apps.

## Refresh virtual entities in Dataverse
Once the code components for canvas apps have been enabled, the next crucial step is to enable the virtual entities used in the Expense mobile app. This action ensures that the canvas app can utilize the most up-to-date metadata of these virtual entities to enhance the overall functionality and user experience of the app. For more information, see [Refresh virtual entities](https://github.com/MicrosoftDocs/dynamics-365-unified-operations-public/blob/9ae4c7446f720f42f694048cd3561515569b7e98/articles/fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md#refresh-virtual-entity-metadata)

The following list shows the entities that need to be refreshed.

- CurrencyEntity
- ExpenseFieldsVisibilityEntity
- LogisticsAddressCountryRegionEntity
- LogisticsAddressCountryRegionTranslationEntity
- LogisticsAddressStateEntity
- TrvAddressZipcodeEntity
- TrvAdminCustomFieldsEntity
- TrvExpenseCategoryEntity
- TrvExpMobileActivitiesEntity
- TrvExpMobileAddressCityEntity
- TrvExpMobileCompanyinfoEntity
- TrvExpMobileDocumentEntity
- TrvExpMobileExpenseEntity
- TrvExpMobileExpenseFieldVisibilityEntity
- TrvExpMobileItemTaxEntity
- TrvExpMobileProjEntity
- TrvExpMobileProjLinePropertyEntity
- TrvExpMobileReportEntity
- TrvExpMobileTaxGroupEntity
- TrvPayMethodEntity

## Grant access to the mobile app in Dataverse

After the mobile app solution is installed in your Dataverse environment, you must share it with your users. The Expense mobile app is a canvas app. To share it, follow the instructions in [Share a canvas app with your organization](/power-apps/maker/canvas-apps/share-app).

Each relevant user must be assigned a **Basic user** and **Expense mobile user** security role in Dataverse that lets them create a connection for the custom connector. You can assign this role to a Dataverse group team. Then, any user who's a member of that team also has the role. Alternatively, you can assign the role directly to a user.

- To assign a role to a group team, follow the instructions in [Manage the security roles of a team](/power-platform/admin/manage-group-teams#manage-the-security-roles-of-a-team). We recommend that you use group teams if you must assign the role to multiple users. For information about how to manage team members, see [Manage team members](/power-platform/admin/manage-teams#manage-team-members).
- To assign a role directly to a user, follow the instructions in [Assign a security role to a user](/power-platform/admin/assign-security-roles).



