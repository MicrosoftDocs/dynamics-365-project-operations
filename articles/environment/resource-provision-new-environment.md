---
title: Provision a new environment
description: 
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Provision a new environment

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article walks through required steps to provision a new Project Operations environment for resource/ non stocked scenarios.

## Enable Project Operations automated provisioning in LCS project

Use following steps to enable Project Operations automated provisioning flow for your LCS Project:

1. Navigate to [LCS page](https://lcs.dynamics.com/v2) and click on a tile **Preview Feature management**.
2. In the Preview feature list select Project Operations feature and enable it by selecting a flag Preview feature enabled.

> [!NOTE]
> This step has to be performed only one time per LCS project.

## Provision Project Operations environment

Start new Finance and Operations [demo environment](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment) or [sandbox/ production environment](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure) deployment. Fill in environment provisioning wizard as described in referenced article. **Make sure selected application version is 10.0.13 or higher.**

For Project Operations provisioning, within Advance settings, select Common Data Service menu item. Enable the Common Data Service Setting to **Yes** , then complete the required fields: Name, Region, Language, Currency and set the Common Data Service Template to Project Operations.

![Deployment Settings](1DeploymentSettings.png)

Important: Select **Agree** to acknowledge the terms of service and the select **Done** to return to the deployment settings.

![Deployment Consent](2DeploymentConsent.png)

Complete remaining required fields in the wizard and confirm the deployment. Environment provisioning time varies based and the environment type and might take up to 6 hours.

Once deployment completes successfully, the environment will show in the Deployed state.

To confirm the environment has deployed successfully, use the Login button, and log on to environment to confirm it is up and running.

![Environment Details](3EnvironmentDetails.png)

 You should see the F&amp;O UI as below.

![F&O Environment](4FOEnvironment.png)

## Apply updates to Finance and Operations environment

Project Operations requires Finance and Operations environment with an application version **10.0.13 (10.0.569.20009)** or higher.

You might need to apply quality updates to Finance and Operations environment to receive this version.

Start in LCS Environment Details page. Find section **Available Updates** and click **View Update** button.

![View Updates](5ViewUpdates.png)

In the next screen select **Save package.**

![Save package](6SavePackage.png)

Select all and save the package.

![Review and save updates](7ReviewAndSaveUpdates.png)

Give package a name and description and confirm saving. Depending on the internet connection this process will take some time.

![Upload package to Assets Library](8UploadPackageToAssetsLibrary.png)

Once package is saved **Done** button will be enabled. Click it to save this package to your LCS project Assets library.

Saving and validating the package might take ~15 minutes.

To apply the update, navigate to LCS Environment details page and select Maintain\&gt; Apply updates

![Maintain Environments](9MaintainEnvironment.png)

In the updates list select the package created in the previous steps and select Apply.

![Apply Updates](10ApplyUpdates.png)

Environment servicing will take some time. Once it is complete, environment will return to deployed state.

![Environment Deployed](11EnvironmentDeployed.png)

## Establish Dual Write connection between CE and F&amp;O Environments

Navigate to LCS project environment details page.

Under Common Data Service Environment Information, select **Link to CDS for Apps.**

Once completed the LCS UI update to indicate the linking was successfully completed. Select **Link to CDS for Apps**. You will be redirected to Dual Write within Finance and Operations.

![Link to CDS](12LinkToCDS.png)

To access the entities to be mapped in the integration, select **Apply Solution** from the menu.

![Apply Solutions](13ApplySolutions.png)

Select Both solutions, **Dynamics 365 Finance and Operations Dual Write Entity Map** s and **Dynamics 365 Project Operations Dual Write Entity Maps** and select **Apply.**

![Confirm Solutions](14ConfirmSolutions.png)

Once the solutions have been applied, the Dual Write entities will be applied to the environment.

![Applying Solutions](15ApplyingSolutions.png)

Once complete, all available mappings will be listed in the environment.

![Dual Write Maps](15DWMappings.png)

## Refresh the data entities after the update

Navigate to Data management workspace in Finance and Operations environment:

![Data Management workspace](D16DataManagement.png)

Open Framework parameters tile:

![Framework Parameters](17FrameworksParameters.png)

In Entity settings page select Refresh Entity list button

![Refresh Entity List](18RefreshEntityList.png)

Refresh is going to take some time (~20 minutes). You will get an alert once it is complete.

![Refresh Confirmation](19RefreshConfirmation.png)

## Run Project Operations Dual Write maps

Navigate to LCS project environment details page.

Under Common Data Service Environment Information, select **Link to CDS for Apps.** Once selected, you will be redirected to the list of entities in the mappings.

Start the maps as described in the table below (following the sequence):

| **Entity Map** | **Refresh entity** | **Initial sync** | **Master for initial sync** | **Run prerequisites** | **Prerequisites initial sync** |
| --- | --- | --- | --- | --- | --- |
| **Project Resource Roles for All Companies (bookableresourcecategories)** | No | Yes | Common Data Service | No | N\A |
| **Legal entities (cdm\_companies)** | No | Yes | Finance and Operations apps | No | N\A |
| **Project Operations integration actuals (msdyn\_actuals)** | No | No | N\A | Yes | No |
| **Project contract lines (salesorderdetails)** | No | No | N\A | No | No |
| **Integration entity for project transaction relationships (msdyn\_transactionconnections)** | No | No | N\A | No | N\A |
| **Project Operations integration contract line milestones (msdyn\_contractlinesscheduleofvalues)** | No | No | N\A | No | N\A |
| **Project Operations integration entity for expense estimates (msdyn\_estimateslines)** | No | No | N\A | No | N\A |
| **Project Operations integration entity for hour estimates (msdyn\_resourceassignments)** | No | No | N\A | No | N\A |
| **Project Operations integration project expenses export entity (msdyn\_expenses)** | Yes | No | N\A | No | N\A |
| **Project Operations integration entity for hour estimates (msdyn\_resourceassignments)** | Yes | No | N\A | No | N\A |

To refresh the entity open the it&#39;s details by clicking on the map name and click Refresh entities button. Proceed with running the map once refresh is complete.

![Refresh Map](20RefreshMapping.png)

Make sure the map in the table is in Running state before you proceed with enabling the next map. Running maps with larger number of prerequisites might take some time.

To run a map with prerequisites, turn on toggle Show related entity maps. If table indicates Prerequisite initial sync as No, make sure initial sync flag is OFF in all the prerequisite maps before running it.

![Run Map](21RunMap.png)

Lastly validate all Project related maps are in the running state:

![All Maps Running](22AllMapsRunning.png)

You have now successfully provisioned and configured Project Operations environment.
