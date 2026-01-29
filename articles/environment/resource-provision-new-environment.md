---
title: Provision a new environment
description: This article provides information about how to provision a new Project Operations environment.
author: mukumarm
ms.author: mukumarm
ms.date: 01/28/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Provision a new environment

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article provides information about how to provision a new Dynamics 365 Project Operations environment for Project Operations Integrated with ERP based scenarios.

## Enable Project Operations automated provisioning in an Lifecycle Services project

Use following steps to enable the Project Operations automated provisioning flow for your Lifecycle Services project.

1. Go to [Lifecycle Services](https://lcs.dynamics.com/v2) and select the **Preview Feature management** tile.
2. In the **Preview feature** list, select **Project Operations Feature**, and then select **Preview feature enabled** to enable Project Operations.

   > [!NOTE]
   > This step is performed only one time per Lifecycle Services project.

## Provision a Project Operations environment

1. Open a new Dynamics 365 Finance [demo environment](/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment) or [sandbox/ production environment](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure) deployment.
1. Walk through the **Environment provisioning** wizard.

   > [!IMPORTANT]
   > Make sure selected application version is 10.0.13 or higher.

1. To provision Project Operations, under **Advance settings**, select **Common Data Service**.
1. Enable the **Common Data Service Setting** by selecting **Yes** and then enter information in the required fields:

- Name
- Region
- Language
- Currency

1. In the **Common Data Service Template** field, select **Project Operations**
1. Select the environment type for your deployment. A subscription-based trial will let you deploy a CDS environment for 30 days.

     :::image type="content" source="./media/1DeploymentSettings.png" alt-text="Screenshot of the deployment settings configuration page.":::

    > [!IMPORTANT]
    > Select **Agree** to acknowledge the terms of service and then select **Done** to return to the deployment settings.
    >
    >:::image type="content" source="./media/2DeploymentConsent.png" alt-text="Screenshot of the deployment consent dialog.":::

1. Optional - Apply demo data to the environment. Go to **Advanced settings**, select **Customize SQL Database Configuration**, and set **Specify a dataset for Application database** to **Demo**.
1. Complete the remaining required fields in the wizard and confirm the deployment. The time to provision the environment varies based on the environment type. Provisioning might take up to six hours.

   After the deployment completes successfully, the environment will show as **Deployed**.

1. To confirm that the environment has deployed successfully, select **Login** and log on to the environment to confirm.

    :::image type="content" source="./media/3EnvironmentDetails.png" alt-text="Screenshot of the environment details page showing deployment status.":::

## Apply updates to the Finance environment

Project Operations requires a Finance environment with application version **10.0.13 (10.0.569.20009)** or higher.

You might need to apply quality updates to your Finance environment to receive this version.

1. In Lifecycle Services, on the **Environment details** page, in the **Available Updates** section, select **View Update**.

    :::image type="content" source="./media/5ViewUpdates.png" alt-text="Screenshot of the view updates option in the available updates section.":::

1. On the **Binary updates** page, select **Save package.**

    :::image type="content" source="./media/6SavePackage.png" alt-text="Screenshot of the save package button on the binary updates page.":::

1. Select **Select all** and then select **Save package**.

    :::image type="content" source="./media/7ReviewAndSaveUpdates.png" alt-text="Screenshot of the review and save updates dialog.":::

1. Enter a name and a description of the package, and then select **Save**. Depending on the internet connection, this process might take some time.

    :::image type="content" source="./media/8UploadPackageToAssetsLibrary.png" alt-text="Screenshot of uploading package to assets library.":::

1. After the package is saved, select **Done** and save this package to the Assets library in your Lifecycle Services project.

   Saving and validating the package might take ~15 minutes.

1. To apply the update, navigate to the **Environment details** page in Lifecycle Services and select **Maintain** > **Apply updates**.

    :::image type="content" source="./media/9MaintainEnvironment.png" alt-text="Screenshot of the maintain environment options.":::

1. In the updates list select the package you created, and select **Apply**.

    :::image type="content" source="./media/10ApplyUpdates.png" alt-text="Screenshot of applying updates from the updates list.":::

   Environment servicing will take some time. After it is complete, the environment will return to a deployed state.

    :::image type="content" source="./media/11EnvironmentDeployed.png" alt-text="Screenshot of the environment deployed status.":::

## Establish a Dual Write connection

1. In your Lifecycle Services project, go to the **Environment details** page.
1. Under **Common Data Service Environment Information**, select **Link to CDS for Apps**.
1. After the link is complete, select **Link to CDS for Apps** again. You will be redirected to Dual Write in Finance.

    :::image type="content" source="./media/12LinktoCDS.png" alt-text="Screenshot of the link to CDS for Apps option.":::

1. Select **Apply Solution** to access the entities that will be mapped in the integration.

    :::image type="content" source="./media/13ApplySolutions.png" alt-text="Screenshot of the apply solution button.":::

1. Select both solutions, **Dynamics 365 Finance Dual Write Entity Map** and **Dynamics 365 Project Operations Dual Write Entity Maps**, and then select **Apply**.

    :::image type="content" source="./media/14ConfirmSolutions.png" alt-text="Screenshot of confirming solutions selection.":::

    After the solutions are applied, the Dual Write entities are applied to the environment.

    :::image type="content" source="./media/15ApplyingSolutions.png" alt-text="Screenshot of the applying solutions progress.":::

    After the entities are applied, all available mappings are listed in the environment.

    :::image type="content" source="./media/15DWMappings.png" alt-text="Screenshot of the dual write mappings list.":::

## Refresh the data entities after the update

1. In Finance, go to the **Data management** workspace.

    :::image type="content" source="./media/16DataManagement.png" alt-text="Screenshot of the data management workspace.":::

1. Select the **Framework parameters** tile.

    :::image type="content" source="./media/17FrameworkParameters.png" alt-text="Screenshot of the framework parameters tile.":::

1. On the **Entity settings** page, select **Refresh Entity list**.

    :::image type="content" source="./media/18RefreshEntityList.png" alt-text="Screenshot of the refresh entity list option.":::

The refresh is going to take approximately 20 minutes. You will receive an alert when it is complete.

  :::image type="content" source="./media/19RefreshConfirmation.png" alt-text="Screenshot of the refresh confirmation message.":::

## Update security settings on Project Operations on Dataverse

1. Go to Project Operations on your Dataverse environment.
1. Go to **Settings** > **Security** > **Security roles**.
1. On the **Security roles** page, in the list of roles, select **dual-write app user** and select the **Custom Entities** tab.  
1. Verify that the role has **Read** and **Append To** permissions for the following entities:

      - **Currency Exchange Rate Type**
      - **Chart Of Accounts**
      - **Fiscal Calendar**
      - **Ledger**
      - **Company**
      - **Expense**

1. After the security role is updated, go to **Settings** > **Security** > **Teams**, and select the default team in the **Local Business Owner** team view.
1. Select **Manage Roles** and verify that the **dual-write app user** security privilege is applied to this team.

## Run Project Operations Dual Write maps

1. In your Lifecycle Services project, go to the **Environment details** page.
1. Under **Common Data Service Environment Information**, select **Link to CDS for Apps.** After you select the link, you will be redirected to the list of entities in the mappings.
1. Start the maps. For more information, see [Project Operations dual-write map versions](resource-dual-write-maps.md#project-operations-dual-write-maps)
1. Validate all project related maps are in the running state.

    :::image type="content" source="./media/22AllMapsRunning.png" alt-text="Screenshot of all maps in running state.":::

## Apply configuration data in CDS for Project Operations (optional)

If you have applied demo data to the Finance environment, see [Set up and apply configuration data in the Common Data Service for Project Operations](resource-apply-pro-setup-config-data.md) to apply demo data to CDS environment.

Your Project Operations environment is now provisioned and configured.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
