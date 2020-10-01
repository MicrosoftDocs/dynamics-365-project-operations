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

1. Navigate to [LCS page](https://lcs.dynamics.com/v2) and click on a tile Preview Feature management.
2. In the Preview feature list select Project Operations feature and enable it by selecting a flag Preview feature enabled.

!Note – this step has to be performed only once per LCS project

## Provision Project Operations environment

Start new Finance and Operations [demo environment](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment) or [sandbox/ production environment](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure) deployment. Fill in environment provisioning wizard as described in referenced article. **Make sure selected application version is 10.0.13 or higher.**

For Project Operations provisioning, within Advance settings, select Common Data Service menu item. Enable the Common Data Service Setting to **Yes** , then complete the required fields: Name, Region, Language, Currency and set the Common Data Service Template to Project Operations.

![](RackMultipart20201001-4-8mzekf_html_2b8da8b858ca175c.png)

Important: Select **Agree** to acknowledge the terms of service and the select **Done** to return to the deployment settings.

![](RackMultipart20201001-4-8mzekf_html_b0f12d2c4ad64bd9.png)

Complete remaining required fields in the wizard and confirm the deployment. Environment provisioning time varies based and the environment type and might take up to 6 hours.

Once deployment completes successfully, the environment will show in the Deployed state.

To confirm the environment has deployed successfully, use the Login button, and log on to environment to confirm it is up and running.

![](RackMultipart20201001-4-8mzekf_html_520e4fa86b8f6f05.png)

 You should see the F&amp;O UI as below.

![](RackMultipart20201001-4-8mzekf_html_2d2bf4c72cee1ca8.png)

## Apply updates to Finance and Operations environment

Project Operations requires Finance and Operations environment with an application version **10.0.13 (10.0.569.20009)** or higher.

You might need to apply quality updates to Finance and Operations environment to receive this version.

Start in LCS Environment Details page. Find section **Available Updates** and click **View Update** button.

![](RackMultipart20201001-4-8mzekf_html_3ab0b27e88610dc6.png)

In the next screen select **Save package.**

![](RackMultipart20201001-4-8mzekf_html_9c0381f57757d094.png)

Select all and save the package.

![](RackMultipart20201001-4-8mzekf_html_d8f872036babbbe6.png)

Give package a name and description and confirm saving. Depending on the internet connection this process will take some time.

![](RackMultipart20201001-4-8mzekf_html_e415cd86de8b8941.png)

Once package is saved **Done** button will be enabled. Click it to save this package to your LCS project Assets library.

Saving and validating the package might take ~15 minutes.

To apply the update, navigate to LCS Environment details page and select Maintain\&gt; Apply updates

![](RackMultipart20201001-4-8mzekf_html_c17a3dfdddb136b9.png)

In the updates list select the package created in the previous steps and select Apply.

![](RackMultipart20201001-4-8mzekf_html_8154cac4215e1d10.png)

Environment servicing will take some time. Once it is complete, environment will return to deployed state.

![](RackMultipart20201001-4-8mzekf_html_d12b350a24251c2a.png)

## Establish Dual Write connection between CE and F&amp;O Environments

Navigate to LCS project environment details page.

Under Common Data Service Environment Information, select **Link to CDS for Apps.**

Once completed the LCS UI update to indicate the linking was successfully completed. Select **Link to CDS for Apps**. You will be redirected to Dual Write within Finance and Operations.

![](RackMultipart20201001-4-8mzekf_html_a8b4a45ec5b3c95b.gif) ![](RackMultipart20201001-4-8mzekf_html_905cf1b404db08d9.png)

To access the entities to be mapped in the integration, select **Apply Solution** from the menu.

![](RackMultipart20201001-4-8mzekf_html_55c53047f4779e9e.gif) ![](RackMultipart20201001-4-8mzekf_html_4299a8224f4a5906.png)

Select Both solutions, **Dynamics 365 Finance and Operations Dual Write Entity Map** s and **Dynamics 365 Project Operations Dual Write Entity Maps** and select **Apply.**

![](RackMultipart20201001-4-8mzekf_html_be2f56311ab06753.png)

Once the solutions have been applied, the Dual Write entities will be applied to the environment.

![](RackMultipart20201001-4-8mzekf_html_13046a47248267a7.png)

Once complete, all available mappings will be listed in the environment.

![](RackMultipart20201001-4-8mzekf_html_a459bd3524d3d1ff.png)

## Refresh the data entities after the update

Navigate to Data management workspace in Finance and Operations environment:

![](RackMultipart20201001-4-8mzekf_html_b593f17127f8c595.png)

Open Framework parameters tile:

![](RackMultipart20201001-4-8mzekf_html_e4ec97db596999db.png)

In Entity settings page select Refresh Entity list button

![](RackMultipart20201001-4-8mzekf_html_56df0739354a84d9.png)

Refresh is going to take some time (~20 minutes). You will get an alert once it is complete.

![](RackMultipart20201001-4-8mzekf_html_cf93324ce2819a8b.png)

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

![](RackMultipart20201001-4-8mzekf_html_47d21e5041babcb0.png)

Make sure the map in the table is in Running state before you proceed with enabling the next map. Running maps with larger number of prerequisites might take some time.

To run a map with prerequisites, turn on toggle Show related entity maps. If table indicates Prerequisite initial sync as No, make sure initial sync flag is OFF in all the prerequisite maps before running it.

![](RackMultipart20201001-4-8mzekf_html_2205ca99f4ca591d.png)

Lastly validate all Project related maps are in the running state:

![](RackMultipart20201001-4-8mzekf_html_a35492dd52ec4232.png)

You have now successfully provisioned and configured Project Operations environment.
