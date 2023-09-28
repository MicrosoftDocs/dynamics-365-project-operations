---
title: Install and configure the Expense mobile app 
description: This article explains how to install and configure the Expense mobile app.
author: mukumarm
ms.date: 08/11/2023
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
- 10.0.35 - 10.0.1627.120 or later
- 10.0.36 - 10.0.1695.68 or later
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

Next, you must configure the connector to the mobile app.

## Configure the Expense Core Service Connector

The Expense Mobile app uses the Expense Core Service Connector (a Power Apps custom connector) for all its interactions with Dataverse.

Configuration has two steps:

1. App registration in Azure Active Directory (Azure AD)
2. Configuration of the custom connector by using the details of the registered app

The following sections explain how to complete these steps.

### App registration in Azure AD

This section explains how to register the Expense mobile app in Azure AD for the connector. In this way, you grant the connector permission to call the app in Dataverse APIs.

> [!NOTE]
> The steps in this section are specific to registration of the Expense mobile app in Azure AD. For more information about how to register apps in Azure AD, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

#### Prerequisites

Before you can register the Expense mobile app in Azure AD, the following prerequisites must be completed:

- You must have an Azure account that has an active subscription.
- The Azure tenant must be the same tenant where the Power Platform environment is installed and configured.
- The Azure account must have permission to manage applications in Azure AD. The following Azure AD roles include the required permissions:

    - Application administrator
    - Application developer
    - Cloud application administrator

#### <a id="register"></a>Register the Expense mobile app in Azure AD

To register the Expense mobile app in Azure AD, follow these steps.

1. Open the [Azure portal](https://portal.azure.com/).
1. Go to **Azure Active Directory \> App registrations**.
1. On the **App registrations** page, select **New registration**.

    :::image type="content" source="media/newexpensemobile/4.NewAppRegistrations.png" alt-text="Screenshot that shows the New registration button on the App registrations page.":::

1. On the **Register an application** page, follow these steps:

    1. In the **Name** field, enter a descriptive and meaningful name for the app.
    1. In the **Supported account types** section, select the appropriate options.
    1. In the **Redirect Uri (optional)** section, select **Web** in the drop-down list, and then enter `https://global.consent.azure-apim.net/redirect` in the text box.
    1. Select **Register** at the bottom of the page.

    After the app is registered, the app registration details page appears.

1. On the app registration details page, follow these steps:

    1. In the **Essentials** section, copy the value of the **Application (client) ID** field, and store it for later use.
    1. On the left menu, under **Manage**, select **API permissions**.

    :::image type="content" source="media/newexpensemobile/6.NewAppRegisterationAPIPersmission.png" alt-text="Screenshot that shows the Application (client) ID field and the API permissions menu item on the app registration details page.":::

1. On the **Configured permissions** page, select **Add a permission**.
1. In the **Request API permissions** dialog box, follow these steps:

    1. On the **Microsoft APIs** tab, select **Dynamics CRM**.

        :::image type="content" source="media/newexpensemobile/7.NewAppRegisterationRequestAPIPermission.png" alt-text="Screenshot that shows the Dynamics CRM API in the Request API permissions dialog box.":::

        > [!TIP]
        > If you can't find **Dynamics CRM** on the **Microsoft APIs** tab, select the **APIs my organization uses** tab. Then search for "Dataverse" (or "00000007-0000-0000-c000-000000000000"), and select it. The remaining steps of this procedure remain the same.

    1. Select **Delegated permissions**.
    1. Select the **user\_impersonation** checkbox.
    1. Select **Add permissions**.

1. On the app registration details page, on the left menu, under **Manage**, select **Certificates & secrets**.
1. On the **Certificates & secrets** page, on the **Client secrets** tab, select **New client secret**.
1. In the **Add a client secret** dialog box, follow these steps:

    1. In the **Description** field, enter a description of the secret.
    1. In the **Expires** field, select an appropriate expiration period.
    1. Select **Add**.

1. On the app registration details page, the **Client secrets** tab now shows the new client secret. Copy the value by selecting the copy button, and store it for later use.

    :::image type="content" source="media/newexpensemobile/11.ClientSecretKey.png" alt-text="Screenshot that shows the copy button for the Value field on the Client secrets tab of the Certificates & secrets page.":::

### Configuration of the custom connector by using the details of the registered app

Now that the Azure AD app is registered and configured, you can configure the Expense Core Service Connector to interact with Dataverse.

#### Prerequisites

The Power Apps account must have permission to perform administrative actions in the target environment. This permission is typically included in the **Environment Admin** or **System Administrator** security role in Dataverse.

#### Configure the Expense Core Service Connector

To configure the Expense Core Service Connector, follow these steps.

1. Open the [Power Apps maker portal](https://make.powerapps.com/), sign in, and select the environment where you've installed the _Dynamics 365 Expense Mobile_ package.
1. Select **Solutions**.
1. On the **Solutions** page, select **Dynamics 365 Expense Mobile**.
1. Select **Expense Core Service Connector**.

    You're redirected to the Power Automate portal on a new browser tab or in a new browser window. You might be asked to sign in again.

1. On the landing page, follow these steps:

    1. Review the value of the **Redirect URL** field. The URL must match the redirect URI that you entered in step 4 of the [Register the Expense mobile app in Azure AD](#register) section.
    1. Select **Edit** in the upper-right corner of the page.

1. On the **Connector Configuration** page, on the **1. General** tab, follow these steps:

    1. In the **Scheme** field group, select the **HTTPS** option.
    1. In the **Host** field, replace the current value with the domain of your organization. For example, if the URL of your organization is `https://operations-demo.crm.dynamics.com/`, enter **operations-demo.crm.dynamics.com**.
    1. In the **Base URL** field, leave the default value as is (**/api/data/v9.2/**).
    1. Select the **Security** button at the bottom of the page or the **2. Security** tab at the top.

    :::image type="content" source="media/newexpensemobile/17.ConnectorGeneralTab.png" alt-text="Screenshot that shows the Scheme field group, the Host field, and the Security button on the one. General tab of the Connector Configuration page.":::

1. On the **2. Security** tab, follow these steps:

    1. In the **Authentication type** section, select **Edit** so that you can provide the Azure AD information for the app.
    1. In the **Client id** field, enter the **Application (client) ID** value that you copied in step 5 of the [Register the Expense mobile app in Azure AD](#register) section.
    1. In the **Client secret** field, enter the secret value that you copied in step 11 of the [Register the Expense mobile app in Azure AD](#register) section.
    1. In the **Resource URL**, enter the URL of your organization (including the scheme). For example, enter `https://operations-demo.crm.dynamics.com`.
    1. Leave the other fields on the tab set to their default values. The following table shows those values, in case you accidentally change or delete them.

        | Field | Value |
        |---|---|
        | Choose what authentication is implemented using your API | **OAuth 2.0** |
        | Identity Provider | **Azure Active Directory** |
        | Enable Service Principal support | Cleared |
        | Login URL | `https://login.windows.net` |
        | Tenant ID | **common** |

    1. Select **Update connector** at the top of the page.

    :::image type="content" source="media/newexpensemobile/19.ConnectorUpdate.png" alt-text="Screenshot that shows the fields and the Update connector button on the two. Security tab of the Connector Configuration page.":::

1. The Expense Core Service Connector is configured for use with the mobile app. Select **Close**, and close the Power Automate portal.

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



