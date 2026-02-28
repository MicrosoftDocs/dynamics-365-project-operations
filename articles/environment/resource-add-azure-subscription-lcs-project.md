---
title: Add an Azure subscription to an Lifecycle Services project
description: This article provides information about how to connect your Azure subscription to an Lifecycle Services project.
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.custom:
  - bap-template
  - sfi-image-nochange

---

# Add an Azure subscription to a Lifecycle Services project

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

You must use an existing Azure subscription to deploy cloud-hosted environments. This article explains how to connect your existing Azure subscription to a Lifecycle Services project. 

## Grant admin consent

1. In your Lifecycle Services project, in the **Environments** section, select **Microsoft Azure settings**.

:::image type="content" source="./media/1MicrosoftAzureSettings.png" alt-text="Screenshot of Microsoft Azure Settings.":::

1. On the **Project settings** page, on the **Azure connectors** tab, select **Authorize**. This action enables you to deploy environments to this project.

:::image type="content" source="./media/2AzureConnectors.png" alt-text="Screenshot of Azure Connectors.":::

1. Select **Authorize** again to provide admin consent.

:::image type="content" source="./media/3GrantAdminConsent.png" alt-text="Screenshot of Grant Admin Consent.":::

1. Accept the permissions request.

:::image type="content" source="./media/4AcceptPermissionRequest.png" alt-text="Screenshot of Accept Permission Request.":::

The authorization is now complete. 

:::image type="content" source="./media/5AuthorizationComplete.png" alt-text="Screenshot of Authorization complete.":::

## <a name="provide"></a>Provide Dynamics Deployment Services access to your Azure subscription

1. Go to [Microsoft Azure billing](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade) and select your subscription. Dynamics Deployment Services needs to access this subscription to deploy environments.

:::image type="content" source="./media/6AzureSubscription.png" alt-text="Screenshot of Azure Subscription Details.":::

1. Select **Access control (IAM)** in the navigation pane, and then select **Add role assignment**.
1. In the slider on the right side, select **Contributor role**, and in the list provided, find and select **Dynamics Deployment Services**. 
1. Select **Save**.

:::image type="content" source="./media/7SubscriptionAccess.png" alt-text="Screenshot of Subscription Access.":::

### Add a subscription connector to an Lifecycle Services project

1. In your Lifecycle Services project, on the **Microsoft Azure settings** page, select **Add** to add a new connector.
1. Enter your Azure subscription ID. You can find your Azure subscription ID in the [Azure portal](https://ms.portal.azure.com/), under  **Settings**  in the lower left of the screen.
1. In the **Configure to use Azure Resource Manager** field, select **Yes**.
1. Make sure Azure's Subscription Microsoft Entra Tenant Domain matches the domain-owning Azure subscription that you're using, and select **Next**.
1. On the **Microsoft Azure Setup** screen, select **Next** to confirm. If you receive an error on this screen, return to the section [Provide Dynamics Deployment Services access to Azure subscription](#provide) in this article and make sure you completed all of the steps.
1. Download the Azure Management Certificate to a local folder on your computer. Ask your Azure subscription administrator to upload the certificate to Azure Management Portal by selecting the subscription and going to **Settings** > **Management Certificates**. This certificate enables Lifecycle Services to communicate with Azure on your behalf. You can skip this step if your user has access to the subscription.
1. Select  **Next**.
1. Select the Azure region to deploy in and select a data center that is close to where you plan to use this system.
1.  Select  **Connect**.

You successfully connected your Azure subscription. You can now deploy Dynamics 365 Finance cloud-hosted environments.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
