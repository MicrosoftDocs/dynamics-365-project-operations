---
title: Apply Dynamics 365 Finance Project Operations demo data
description: T
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Apply Dynamics 365 Finance Project Operations demo data

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

>[**Important**]
> This article is applicable only for Finance and Operations application version 10.0.13 and can be performed only on a Cloud Hosted environment. Perform this step **BEFORE** applying quality updates to the environment described in the next paragraph.

Open LCS environment details page. Note that it has the details needed to connect to the environment via Remote Desktop Protocol (RDP).

![Environment Details](1EnvironmentDetails.png)

First set of highlighted credentials contain hyperlink to remote desktop connection and environment admin username and password. Second set below will be used to log in to SQL Server in this environment.

Remote to the environment by clicking hyperlink in Local Accounts and use the Local Account credentials above to authenticate.

As a first step we will stop the AOS and batch processes so we can continue with replacing the SQL DB.

Navigate to Internet Information Services \&gt; Application Pools \&gt; AOSService and Stop it.

![Stop AOS](2StopAOS.png)

Secondly navigate to Services and stop the following two:

- Microsoft Dynamics 365 Unified Operations: Batch Management Service
- Microsoft Dynamics 365 Unified Operations: Data Import Export Framework

![Stop Services](3StopAOS.png)

Next, let&#39;s open Microsoft SQL Server Management Studio. Login with SQL server credentials and use axdbadmin user and password from LCS Environments details page.

![SQL Server Management Studio](SSMS.png)

Expand Databases in Object Explorer and find AXDB. We will need to replace it with a new database. You can find the SQL database to use in the Download Center. Copy this zip file to the VM you are remoted into and extract zip contents.

In SQL Server Management Studio, right click on AxDB and select Tasks\&gt; Restore\&gt; Database

![Restore Database](5RestoreDatabase.png)

Select Source Device and navigate to the file extracted from zip you have copied previously.

![Source Devices](6SourceDevice.png)

Next go to Options and select  **Overwrite the existing database**  and  **Close existing connections to destination database**. Click OK.

![Restore Settings](7RestoreSetting.png)

Once you will get a confirmation AXDB restore was successful, you can close SQL Services Management Studio.

Navigate back to Internet Information Services \&gt; Application Pools \&gt; AOSService and Start it.

Navigate to Services and Start the two Services we previously stopped.

Next, we will need to find AdminUserProvisioning tool on this VM. For most of the VMs it will be in K:\AosService\PackagesLocalDirectory\bin\AdminUserProvisioning.exe

Run it.  Use your previously created user address in the Email Address field and click Submit.

![Admin User Provisioning](8AdminUserProvisioning.png)

This takes a couple of minutes to complete and should result in a confirmation message that Admin user was successfully updated.

Lastly, run Command Prompt as Administrator and perform iisreset

![IIS Reset](9IISReset.png)

All done! You can close remote desktop session and using LCS Environment Details page log in to the environment to confirm it is up and running:

![Finance and Operations](10FinanceAndOperations.png)
