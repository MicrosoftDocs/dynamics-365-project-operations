---
title: Install and configure the Expense mobile app
description: This article explains how to install and configure the Expense mobile app.
author: ramagadu
ms.date: 05/26/2023
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: ramagadu
ms.custom: bap-template
---

# Install and configure the Expense mobile app

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

> [!IMPORTANT]
> The functionality that's described in this article is available as part of a preview release. The functionality and the content of this article are subject to change. For more information about preview releases, see [One version service updates FAQ](/dynamics365/unified-operations/fin-and-ops/get-started/one-version.md).

This article explains how administrators can prepare your Microsoft Dynamics 365 Finance and Dataverse environments to support the Expense mobile app. It also explains how to install the app on your mobile devices.

## System requirements

To run the Expense mobile app, you must use Dynamics 365 Finance version 10.0.34 with the latest quality update (QU) or later.

## Set up Dataverse for your Dynamics 365 Finance environment

Your Dynamics 365 Finance environment must be linked with a Dataverse environment, If Dataverse isn't already set up for your environment, follow the instructions in [Enable Power Platform Integration](/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration#enable-after-deploy.md).

When you create the Dataverse environment where you want to install the app, be sure to enable Dynamics 365 apps.

## Enable the Expense mobile app in Dynamics 365 Finance

To enable the Expense mobile app in Dynamics 365 Finance, follow these steps.

1. In your Dynamics 365 Finance environment, go to **Workspaces** \> **Feature Management**.
1. In the list, find and select **feature Use expense mobile application for intuitive expense entry experience**, and then select **Enable now**.

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
> The steps in this section are specific to registration of the Expense mobile app in Azure AD. For more information about how to register apps in Azure AD, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app.md).

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

    :::image type="content" source="media/newexpensemobile/17.ConnectorGeneralTab.png" alt-text="Screenshot that shows the Scheme field group, the Host field, and the Security button on the 1. General tab of the Connector Configuration page.":::

1. On the **2. Security** tab, follow these steps:

    1. In the **Authentication type** section, select **Edit** so that you can provide the Azure AD information for the app.
    1. In the **Client id** field, enter the **Application (client) ID** value that you copied in step 5 of the [Register the Expense mobile app in Azure AD](#register) section.
    1. In the **Client secret** field, enter the secret value that you copied in step 11 of the [Register the Expense mobile app in Azure AD](#register) section.
    1. In the **Resource URL**, enter the URL of your organization (including the scheme). For example, enter `https://operations-demo.crm.dynamics.com`.
    1. Leave the other fields on the tab set to their default values. The following table shows those values, in case you accidentally change or delete them.

        | Field | Value |
        |---|---|
        | Choose what authentication is implemented by your API | **OAuth 2.0** |
        | Identity Provider | **Azure Active Directory** |
        | Enable Service Principal support | Cleared |
        | Login URL | `https://login.windows.net` |
        | Tenant ID | **common** |

    1. Select **Update connector** at the top of the page.

    :::image type="content" source="media/newexpensemobile/19.ConnectorUpdate.png" alt-text="Screenshot that shows the fields and the Update connector button on the 2. Security tab of the Connector Configuration page.":::

1. The Expense Core Service Connector is now configured for use by the mobile app. Select **Close**, and close the Power Automate portal.

## Grant access to the mobile app in Dataverse

After the mobile app solution is installed in your Dataverse environment, you must share it with your users. The Expense mobile app is a canvas app. To share it, follow the instructions in [Share a canvas app with your organization](/power-apps/maker/canvas-apps/share-app.md).

Each relevant user must be assigned a **Basic user** security role that lets them create a connection for the custom connector. You can assign this role to a Dataverse group team. Then, any user who's a member of that team also has the role. Alternatively, you can assign the role directly to a user.

- To assign a role to a group team, follow the instructions in [Manage the security roles of a team](/power-platform/admin/manage-group-teams.md#manage-the-security-roles-of-a-team). We recommend that you use group teams if you must assign the role to multiple users. For information about how to manage team members, see [Manage team members](/power-platform/admin/manage-teams#manage-team-members.md).
- To assign a role directly to a user, follow the instructions in [Assign a security role to a user](/power-platform/admin/assign-security-roles.md).

## Install and open the Expense mobile app

To install and use the Expense mobile app on a mobile device, follow these steps.

1. Install the Power Apps mobile app by following the instructions in [Install the Power Apps mobile app](/power-apps/mobile/run-powerapps-on-mobile.md).
1. Open the Power Apps mobile app, and sign in by using the same corporate account that you use to sign in to Dynamics 365 Finance.
1. Use the **Search** field to search for "Expense Mobile." Because the Expense mobile app is a canvas app, you can add it to your favorites list in Power Apps by swiping left on it after you find it.
1. Open the Expense mobile app, and start to use it. The first time that you open the app, you must create a connection to Expense Core Service Connector by using the same corporate account that you use to sign in to Dynamics 365 Finance.
