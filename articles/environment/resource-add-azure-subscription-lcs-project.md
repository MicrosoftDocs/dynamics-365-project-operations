---
title: Add an Azure subscription to LCS project
description: This topic provides information about how to connect your Azure subscription to an LCS project.
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Add an Azure subscription to LCS project

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Cloud-hosted environments must be deployed using an existing Azure subscription. This topic explains how to connect your existing Azure subscription to an LCS project. 

## Grant admin consent

1. In your LCS project, in the **Environments** section, select **Microsoft Azure settings**.

![Microsoft Azure Settings](1MicrosoftAzureSettings.png)

2. On the **Project settings** page, on the **Azure connectors** tab, select **Authorize**. This allows environments to be deployed to this project.

![Azure Connectors](2AzureConnectors.png)

3. Select **Authorize** again to provide admin consent.

![Grant Admin Consent](3GrantAdminConsent.png)

4. Accept the permissions request.

![Accept Permission Request](4AcceptPermissionRequest.png)

Note that the authorization is now complete. 

![Authorization Successfull](5AuthorizationComplete.png)

## <a name="provide"></a>Provide Dynamics Deployment Services access to your Azure subscription

1. Go to [Microsoft Azure billing](https://portal.azure.com/#blade/Microsoft\_Azure\_Billing/SubscriptionsBlade) and select your subscription. Dynamics Deployment Services needs to access this subscription to be able to deploy environments.

![Azure Subscription Details](6AzureSubscription.png)

2. Select **Access control (IAM)** in the navigation pane, and then select **Add role assignment**.
3. In the slider on the right side, select **Contributor role**, and in the list provided, find and select **Dynamics Deployment Services**. 
4. Select **Save**.

![Subscription Access](7SubscriptionAccess.png)

### Add a subscription connector to an LCS project

1. In you LCS project, on the **Microsoft Azure settings** page, select **Add** to add a new connector.
2. Enter your Azure subscription ID. You can find your Azure subscription ID in the [Azure Portal](https://ms.portal.azure.com/), under  **Settings**  in the lower left of the screen.
3. In the **Configure to use Azure Resource Manager** field, select **Yes**.
4. Make sure Azure's Subscription AAD Tenant Domain matches the domain-owning Azure subscription that you are using, and select **Next**.
5. On the **Microsoft Azure Setup** screen select **Next** to confirm. If you receive an error on this screen, return to the section [Provide Dynamics Deployment Services access to Azure subscription](#provide) in this toic and make sure you have completed all of the steps.
6. Download the Azure Management Certificate to a local folder on your computer, and then upload it to Azure Management Portal by going to **Settings** > **Management Certificates**. This certificate will enable LCS to communicate with Azure on your behalf. You can skip this step if your user has access to the subscription.
7. Select  **Next**.
8. Select the Azure region to deploy in and select a data center that is close to where you plan to use this system.
9.  Select  **Connect**.

You have successfully connected your Azure subscription. You can now deploy Dynamics 365 Finance cloud-hosted environments.


