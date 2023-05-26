---
title: Install and configure expense mobile app 
description: This article provides information about installing and configure new expense mobile app.
author: ramagadu
ms.date: 05/26/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# Install and configure Expense mobile app

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

> [!IMPORTANT]
>The functionality that's described in this article is available as part of a preview release. The functionality and the content of this article are subject to change.  For more information about preview releases, see [**One version service updates FAQ**](https://learn.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

This article describes how administrators can prepare your Microsoft Dynamics 365 Finance and Dataverse environments to support the Expense mobile app. It also describes how to install the app on your mobile devices.

## System requirements

To run the Expense mobile app, you must be using Dynamics 365 Finance version 10.0.34 with latest quality update(QU) or later.

## Set up Dataverse for your Dynamics 365 Finance environment

Dynamics 365 Finance environment must be linked with a Dataverse environment, If Dataverse isn't already set up for your environment, follow the instructions in [Enable Power Platform Integration - Finance & Operations](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration#enable-after-deploy)

When you create the Dataverse environment where you want to install the app, be sure to enable Dynamics 365 apps.

## Enable the feature in Dynamics 365 Finance

1. Go to **Dynamics 365 Finance** environment
2. Go to  **Workspaces**  \>  **Feature Management**.
3. In the list, find and select  **feature Use expense mobile application for intuitive expense entry experience** , and then select  **Enable now**.

## Install the mobile app in Dataverse

You must install the Expense mobile app in your Dataverse environment to enable users to access it when they sign in by using the Power Apps mobile app.

1. Go to ["Dynamics 365 Expense Mobile Application (Public Preview)" in Microsoft AppSource.](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.msdyn_expense_mobile-preview?flightCodes=d365expensemobile&exp=ubp8)
2. Select **Get it now** 
   :::image type="content" source="media/newexpensemobile/1.ExpenseMobile-AppSource.png" alt-text="Expense mobile app in App source"::: 
3. You will be redirected to Power Platform Admin Center(PPAC) and window will appear to install the application, please select the environment where you would like to install the app and click on Install button. In this scenario, please select the environment that you have created/updated environment earlier.
:::image type="content" source="media/newexpensemobile/2.InstallExpenseMobileDataverseBlade.png" alt-text="Install mobile app in a Dataverse environment."::: 
1. Upon successful installation of application, you will see the app under the Apps in the environment and a solution under the solutions tab.
:::image type="content" source="media/newexpensemobile/3.ExpenseMobileSolutionInPPAC.png" alt-text="Power apps solutions"::: 

As a next step, you would need to configure the connector the mobile app. Please follow the below steps to configure the connector.

## Expense Core Service Connector Configuration

Expense Mobile app uses **Expense Core Service Connector** (Power Apps Custom Connector) for all its interactions with Microsoft Dataverse.

It has two steps:

  1. App registration in Azure Active Directory
  2. Configure the custom connector using the registered app details.

## App registration

The steps below describe the specific process of registering an app in Azure AD for the connector. This is required to grant permissions to the connector to call in Dataverse APIs.

Note: Scope of these steps are quite specific. [Click here](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app), for more information on registering an application with Azure AD.

### Prerequisites

- An Azure account that has an active subscription.
- The Azure tenant must be the same one where Power platform environment is installed and configured.
- The Azure account must have permission to manage applications in Azure AD. Any of the following Azure AD roles include the required permissions:
  - Application administrator
  - Application developer
  - Cloud application administrator

#### Steps

1. Open [Azure Portal](https://portal.azure.com/) and navigate to **Azure Active Directory \> App registrations**. Once on the page, select **New Registration,** as shown in the below given image.
:::image type="content" source="media/newexpensemobile/4.NewAppRegistrations.png" alt-text="App registrations page to create an app in Azure"::: 

1. Once **Register an application** page loads:
     1. Enter a descriptive and meaningful name of the application in **Name**
     2. Select the appropriate options **Supported account types**
     3. Select **Redirect Uri** as **Web** and enter [_https://global.consent.azure-apim.net/redirect_](https://global.consent.azure-apim.net/redirect)as the value in the provided textbox.
     4. Click on the **Register** button provided at the bottom of the page.

    :::image type="content" source="media/newexpensemobile/5.NewRegisterAnApplicationDetails.png" alt-text="App registrations details page to enter the name and other key details"::: 
    
2. Once the application is registered, you will now be redirected to its details page.
     1. Copy the value/ID provided against **Application (client) ID** in the Essentials section and store it for later use.
     2. Click on **API permissions** from the left menu blade.

     :::image type="content" source="media/newexpensemobile/6.NewAppRegisterationAPIPersmission.png" alt-text="App registrations home page to copy the client Id and navigate to API permissions"::: 

3. Once **API permissions** page loads, select **Add a permission** from Configured permissions section to bring up **Request API permissions** blade and select **Dynamics CRM** from Microsoft APIs tab.
 :::image type="content" source="media/newexpensemobile/7.NewAppRegisterationRequestAPIPermission.png" alt-text="Request API Permission page to select the Dynamics CRM"::: 

    > [!NOTE]
    > In case you are unable to find Dynamics CRM, select the next tab, APIs my organization uses and search for Dataverse (or 00000007-0000-0000-c000-000000000000) and select it. Rest of the steps remain same.**

1. Select **Delegated permissions** and **user\_impersonation** checkbox, and then click on **Add permissions** button.
 :::image type="content" source="media/newexpensemobile/8.NewAppRegisterationDelegatedPermission.png" alt-text="Request API Permission page to select the Dynamics CRM with delegated permissions"::: 

1. Select **Certificates & secrets** from left blade of your app registration page, select **Client secrets** tab and select **new client secret** as shown in the below given picture. This will open **Add a client secret** blade towards the right.
 :::image type="content" source="media/newexpensemobile/9.CertificatesAndSecretsMainPage.png" alt-text="Client & secret page to create a secret key"::: 

1. In the **Add a client secret** blade, enter a description for the secret and choose an appropriate **expiration period**. Click on **the Add** button to continue.
 :::image type="content" source="media/newexpensemobile/10.AddClientSecretBlade.png" alt-text="Add a client secret blade to create a secret key"::: 

1. Once the blade closes, the newly generated client secret will be displayed. **Copy** this value by clicking on the copy button and store it for later use.
 :::image type="content" source="media/newexpensemobile/11.ClientSecretKey.png" alt-text="Client secret key details"::: 

## Configure Expense Core Service Connector

Now that the Azure AD application is registered and configured, you configure the Expense Core Service Connector to interact with Microsoft Dataverse.

### Prerequisites

  The Power Apps account must have permission to perform administrative actions in the target environment. This permission is typically included in the **Environment Admin** or **System Administrator** security role in Dataverse.

### Steps

1. Go to [Power Apps](https://make.powerapps.com/) Apps, sign-in and select the environment where you have installed the _Dynamics 365 Expense Mobile_ package.
2. Select **Solutions** from left blade
   :::image type="content" source="media/newexpensemobile/12.Solutions.png" alt-text="Power Apps Solutions":::
3. Once the **Solutions** page loads, select **Dynamics 365 Expense Mobile** solution from the list.
   :::image type="content" source="media/newexpensemobile/13.SolutionExpenseMobile.png" alt-text="Power Apps solution list for Expense mobile package"::: 
4. Select **Expense Core Service Connector** from the list. You will be redirected to Power Automate portal in a new tab/browser and maybe asked to sign in again.
   :::image type="content" source="media/newexpensemobile/14.SolutionExpenseCoreServiceConnector.png" alt-text="Expense Core Service Connector"::: 
5. On the landing page, notice the **Redirect URL**. This must be same as the redirect Uri entered in **Step 2** of Azure AD App registration. In case of a difference, please go back to your Azure AD app registration and fix the Uri
   :::image type="content" source="media/newexpensemobile/15.ConnectorDetails.png" alt-text="Connector details":::
6. Click on **Edit** button at the top right corner.
    :::image type="content" source="media/newexpensemobile/16.EditConnector.png" alt-text="Edit connector"::: 

7. Once the Connector Configuration page loads:
   1. Select **General** tab
   2. Set **Scheme** as **HTTPS**
   3. Replace **Host** value with the domain of your organization. For example, if your Organization URL is **https://operations-demo.crm.dynamics.com/**, enter only **operations-demo.crm.dynamics.com**.
   4. Do not modify the default value for **Base URL** value, leave it as-is (/api/data/v9.2/).
   5. Navigate to the Security page, either by clicking **Security -\>** button at the bottom of the page or by selecting **2. Security** tab at the top.

    :::image type="content" source="media/newexpensemobile/17.ConnectorGeneralTab.png" alt-text="Connector general tab details"::: 

8. Once the **Security** tab loads, click on **Edit** button in the **Authentication Type** section.
      :::image type="content" source="media/newexpensemobile/18.ConnectorSecurityEdit.png" alt-text="Connector security tab details"::: 

9. On the security page, provide Azure AD information for the application:
    1. For **Client id,** enter the **Application (client) ID** value you copied in **Step 3** of App registration for Expense Core Service Connector in Azure AD
    2. For **Client secret,** enter the secret value you copied in **Step 8** ofApp registration for Expense Core Service Connector in Azure AD
    3. For **Resource URL** , enter the URL of your Organization (with scheme). For example, [https://operations-demo.crm.dynamics.com](https://operations-demo.crm.dynamics.com/)
    4. Leave the rest of configuration as-is. Please refer to the image below in case they are accidentally changed or deleted.
    5. Once done, click on the **Update connector** button and wait for changes to be saved.

    :::image type="content" source="media/newexpensemobile/19.ConnectorUpdate.png" alt-text="Connector security tab details"::: 

10. Expense Core Service Connector is now configured to be used by the mobile app. You can now click on the **Close** button and also close the Power Automate portal.

## Grant access to the mobile app in Dataverse

After the mobile app solution is installed in your Dataverse environment, you must share it with your users. The Expense mobile app is a canvas app. To share it, follow the instructions in [Share an app](https://learn.microsoft.com/en-us/power-apps/maker/canvas-apps/share-app).

Each relevant user must be assigned with a security role as **Basic user** that lets them to create a connection for custom connector. You can assign this role to a Dataverse group team. Any user who's a member of that team will then have the role too. Alternatively, you can assign the role directly to a user.

- To assign a role to a group team, follow the instructions in [Manage the security roles](https://learn.microsoft.com/en-us/power-platform/admin/manage-group-teams#manage-the-security-roles-of-a-team) of a team. We recommend that you use group teams if you must assign the role to multiple users. For information about how to manage team members, see [Manage team members](https://learn.microsoft.com/en-us/power-platform/admin/manage-teams#manage-team-members).
- To assign a role directly to a user, follow the instructions in [Assign a security role to a user](https://learn.microsoft.com/en-us/power-platform/admin/assign-security-roles).

## Install and open the Expense mobile app

Follow these steps to install and use the Expense mobile app on a mobile device.

1. Install the Power Apps mobile app by following the instructions in [Install the Power Apps mobile app](https://learn.microsoft.com/en-us/power-apps/mobile/run-powerapps-on-mobile).
2. Open the Power Apps mobile app, and sign in by using the same corporate account that you use to sign in to Dynamics 365 Finance.
3. Use the  **Search**  field to search for _Expense Mobile_. Because it's a canvas app, you can add it to your favourites list in Power Apps by swiping left on it after you find it.
4. Open the Expense mobile app, and start to use it. While opening the application for the first time, you are required to create a connection to **Expense Core Service Connector** using the same corporate account that you use to sign in to Dynamics 365 Finance.