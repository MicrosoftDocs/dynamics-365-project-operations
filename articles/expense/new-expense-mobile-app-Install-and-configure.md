---
title: Install and configure the Expense mobile app 
description: This article provides information about how to install and configure the Expense mobile app.
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
>The functionality that's described in this article is available as part of a preview release. The functionality and the content of this article are subject to change.  For more information about preview releases, see [**One version service updates FAQ**](/dynamics365/unified-operations/fin-and-ops/get-started/one-version.md).

This article explains how administrators can prepare your Microsoft Dynamics 365 Finance and Microsoft Dataverse environments to support the Expense mobile app. It also describes how to install the app on your mobile devices.

## System requirements

To run the Expense mobile app, you must use Dynamics 365 Finance version 10.0.34 with latest quality update(QU) or later.

## Set up Dataverse for your Dynamics 365 Finance environment

Your Dynamics 365 Finance environment must be linked with a Dataverse environment, If Dataverse isn't already set up for your environment, follow the instructions in [Enable Power Platform Integration](/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration#enable-after-deploy.md).

When you create the Dataverse environment where you want to install the app, be sure to enable Dynamics 365 apps.

## Enable the Expense mobile app in Dynamics 365 Finance

To enable the Expense mobile app in Dynamics 365 Finance, follow these steps.

1. Go to your **Dynamics 365 Finance** environment.
1. Select **Workspaces** \> **Feature Management**.
1. In the list, find and select **feature Use expense mobile application for intuitive expense entry experience**, and then select **Enable now**.

## Install the mobile app in Dataverse

You must install the Expense mobile app in your Dataverse environment to enable users to access it when they sign in by using the Power Apps mobile app.

To install the Expense mobile app in your Dataverse environment, follow these steps.

1. In Microsoft AppSource, go to [Dynamics 365 Expense Mobile Application (Public Preview)](https://appsource.microsoft.com/product/dynamics-365/mscrm.msdyn_expense_mobile-preview?flightCodes=d365expensemobile&exp=ubp8).
1. Select **Get it now**. 
1. Select the environment created/updated earlier where you want to install the Expense mobile app and then select **Install**.
1. After successful installation, Dynamics 365 Expense Mobile is listed as a **Solution** on the Power Apps **Solutions** tab.

Next, you need to configure the connector to the mobile app. 

## Configure the Expense Core Service Connector

The Expense Mobile app uses the **Expense Core Service Connector** (Power Apps Custom Connector) for all its interactions with Dataverse.

It has two steps:

  1. App registration in Azure Active Directory
  2. Configure the custom connector using the registered app details.

The following sections explain how to regiter the Expense moblile app in Microsoft Azure Active Directory, and configure the custom connector.

### App registration in Azure AD

The following steps describe the process of registering an app in Azure AD for the connector to grant permissions to the connector to call it in Dataverse APIs.

> [!Note]
> These steps are specific to registering the Expense Mobile app in Azure AD. For more information about registering apps in Azure AD, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app.md).

#### Prerequisites

Before you can register the Expense mobile app in Azure AD, the following prerequsites must be completed.

- You must have an Azure account that has an active subscription.
- The Azure tenant must be the same tenant where the Power platform environment is installed and configured.
- The Azure account must have permission to manage applications in Azure AD. Any of the following Azure AD roles include the required permissions:
  - Application administrator.
  - Application developer.
  - Cloud application administrator.

#### Register the Expense mobile app in Azure AD

To register the Expense mobile app in Azure AD, follow these steps.

1. Open the [Azure Portal](https://portal.azure.com/).
1. Go to **Azure Active Directory \> App registrations**. 
1. Select **New Registration,**.
   :::image type="content" source="media/newexpensemobile/4.NewAppRegistrations.png" alt-text="App registrations page to create an app in Azure"::: 
1. On the **Register an application** page:
   1. Enter a descriptive and meaningful name of the application in **Name**.
   1. Select the appropriate options **Supported account types**
   1. In the **Redirect Uri (optional)** section, from the drop down, select **Web** and then type **https://global.consent.azure-apim.net/redirect** in the provided textbox.
   1. Select **Register** button provided at the bottom of the page.
1. Once the application is registered, you'll now be redirected to its details page.
     1. Copy the value/ID provided against **Application (client) ID** in the Essentials section and store it for later use.
     2. Select on **API permissions** from the left menu blade.
     :::image type="content" source="media/newexpensemobile/6.NewAppRegisterationAPIPersmission.png" alt-text="Screenshot of the App registrations home page with the Application (client) ID and the navigate to API permissions highlighted"::: 
1. From the **Configured permissions** page, select **Add a permission** section.
1. From the **Request API permissions** pane, select **Dynamics CRM** from Microsoft APIs tab.
 :::image type="content" source="media/newexpensemobile/7.NewAppRegisterationRequestAPIPermission.png" alt-text="Screenshot of the Request API Permission page with Dynamics CRM highlighted."::: 
    > [!NOTE]
    > If you are unable to find Dynamics CRM, select the next tab, APIs my organization uses and search for Dataverse (or 00000007-0000-0000-c000-000000000000) and select it. Rest of the steps remain same.**
1. Select **Delegated permissions** and check the **user\_impersonation** checkbox
1. Select **Add permissions**.
1. From the Manage section on the left, select **Certificates & secrets**.
1. Select the **Client secrets** tab and then select **+ New client secret** to open **Add a client secret**.
1. From **Add a client secret**, enter a **Description** for the secret and choose an appropriate **expiration period**.
1. Select **Add**.
1. Once the blade closes, the newly generated client secret is displayed. **Copy** this value by selecting the copy button and store it for later use.
   :::image type="content" source="media/newexpensemobile/11.ClientSecretKey.png" alt-text="Screenshot of the Client secrets page with the copy button highlighted"::: 

### Configure the custom connector using the registered app details

Now that the Azure AD application is registered and configured, you configure the Expense Core Service Connector to interact with Microsoft Dataverse.

#### Prerequisites

The Power Apps account must have permission to perform administrative actions in the target environment. This permission is typically included in the **Environment Admin** or **System Administrator** security role in Dataverse.

#### Configure the Expense Core Service Connector

To configure the Expense Core Service Connector, follow these steps.

1. Go to [Power Apps](https://make.powerapps.com/) Apps, sign-in and select the environment where you have installed the _Dynamics 365 Expense Mobile_ package.
1. Select **Solutions**.
1. On the **Solutions** page, select **Dynamics 365 Expense Mobile**.
1. Select **Expense Core Service Connector**. You are redirected to Power Automate portal in a new tab/browser and maybe asked to sign in again.
1. On the landing page, notice the **Redirect URL**. This must be same as the redirect Uri entered instep 4 of Azure AD App registration. 
1. Select the **Edit** button at the top right corner.
1. After the **Connector Configuration** page loads, select **General** tab.
1. Set **Scheme** as **HTTPS**
1. Replace the **Host** value with the domain of your organization. For example, if your Organization URL is **https://operations-demo.crm.dynamics.com/**, enter only **operations-demo.crm.dynamics.com**.
1. Don't modify the default value for **Base URL** value, leave it as-is (/api/data/v9.2/).
1. Navigate to the Security page, by selecting the **Security -\>** button at the bottom of the page or by selecting **2. Security** tab at the top.
   :::image type="content" source="media/newexpensemobile/17.ConnectorGeneralTab.png" alt-text="Screenshot of the Connector general tab details with Scheme, Host, and the Security button highlighted."::: 
1. After the **Security** tab loads, from **Authentication Type** section, select the **Edit** button.
1. On the security page, provide the Azure AD information for the application:
    1. For **Client id,** enter the **Application (client) ID** value that you copied in step 5 of Register the Expense mobile app in Azure AD.
    1. For **Client secret,** enter the secret value you copied in step 11 of Register the Expense mobile app in Azure AD.
    1. For **Resource URL** , enter the URL of your Organization (with scheme). For example, https://operations-demo.crm.dynamics.com.
    1. Leave the rest of configuration as-is. Refer to the image below in case they're accidentally changed or deleted.
    1. Once done, select the **Update connector** button and wait for changes to be saved.
       :::image type="content" source="media/newexpensemobile/19.ConnectorUpdate.png" alt-text="Screenshot of the Connector security tab details"::: 
1. The Expense Core Service Connector is now configured to be used by the mobile app. Select the **Close** button and close the Power Automate portal.

## Grant access to the mobile app in Dataverse

After the mobile app solution is installed in your Dataverse environment, you must share it with your users. The Expense mobile app is a canvas app. To share it, follow the instructions in [Share a canvas app with your organization](/power-apps/maker/canvas-apps/share-app.md).

Each relevant user must be assigned with a security role as **Basic user** that lets them to create a connection for custom connector. You can assign this role to a Dataverse group team. Any user who's a member of that team will then have the role too. Alternatively, you can assign the role directly to a user.

- To assign a role to a group team, follow the instructions in [Manage the security roles of a team](/power-platform/admin/manage-group-teams.md#manage-the-security-roles-of-a-team) of a team. We recommend that you use group teams if you must assign the role to multiple users. For information about how to manage team members, see [Manage team members](/power-platform/admin/manage-teams#manage-team-members.md).
- To assign a role directly to a user, follow the instructions in [Assign a security role to a user](/power-platform/admin/assign-security-roles.md).

## Install and open the Expense mobile app

To install and use the Expense mobile app on a mobile device, follow these steps.

1. Install the Power Apps mobile app by following the instructions in [Install the Power Apps mobile app](/power-apps/mobile/run-powerapps-on-mobile.md).
1. Open the Power Apps mobile app, and sign in by using the same corporate account that you use to sign in to Dynamics 365 Finance.
1. Use the  **Search**  field to search for _Expense Mobile_. Because it's a canvas app, you can add it to your favorites list in Power Apps by swiping left on it after you find it.
1. Open the Expense mobile app, and start to use it. While opening the application for the first time, you're required to create a connection to **Expense Core Service Connector** using the same corporate account that you use to sign in to Dynamics 365 Finance.
