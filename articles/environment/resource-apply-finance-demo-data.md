---
title: Apply demo data to a Finance Cloud-hosted environment
description: This article explains how to apply demo data from Project Operations to a Dynamics 365 Finance Cloud-hosted environment.
author: mukumarm
ms.author: mukumarm
ms.date: 01/28/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Apply demo data to a Finance Cloud-hosted environment

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

> [!IMPORTANT]
> This article is only applicable only Microsoft Dynamics 365 Finance version 10.0.13 and can be performed only on a Cloud-hosted environment. Complete the steps in this article **BEFORE** you apply quality updates to the environment.

1. In your Lifecycle Services project, open the **Environment details** page. Notice that it includes the details needed to connect to the environment by using Remote Desktop Protocol (RDP).

:::image type="content" source="./media/1EnvironmentDetails.png" alt-text="Screenshot of the Environment details page showing connection credentials.":::

The first set of highlighted credentials are the local account credentials and contain a hyperlink to the remote desktop connection. The credentials include the environment admin username and password. The second set of credentials are used to log in to SQL Server in this environment.

1. Remote to the environment by the hyperlink in **Local Accounts**, and use the **Local Account credentials** to authenticate.
1. Go to **Internet Information Services** > **Application Pools** > **AOSService** and stop the service. You are stopping the service at this point so that you can continue to replace the SQL database.

:::image type="content" source="./media/2StopAOS.png" alt-text="Screenshot of stopping the AOSService in Internet Information Services.":::

1. Go to **Services** and stop the following two items:

- Microsoft Dynamics 365 Unified Operations: Batch Management Service
- Microsoft Dynamics 365 Unified Operations: Data Import Export Framework

:::image type="content" source="./media/3StopServices.png" alt-text="Screenshot of stopping the Batch Management and Data Import Export Framework services.":::

1. Open Microsoft SQL Server Management Studio. Log in with SQL server credentials and use the axdbadmin user and password from the Lifecycle Services **Environments details** page.

:::image type="content" source="./media/4SSMS.png" alt-text="Screenshot of SQL Server Management Studio login dialog.":::

1. In Object Explorer, **Databases** and locate **AXDB**. You will replace database with a new database that is located in the [Download Center](https://download.microsoft.com/download/1/a/3/1a314bd2-b082-4a87-abdc-1ba26c92b63d/ProjOpsDemoDataFOGARelease.zip).
1. Copy the zip file to the VM you are remoted into and extract zip contents.
1. In SQL Server Management Studio, right-click **AxDB**, and then select **Tasks** > **Restore** > **Database**.

:::image type="content" source="./media/5RestoreDatabase.png" alt-text="Screenshot of selecting the Restore Database option in SQL Server Management Studio.":::

1. Select **Source Device** and navigate to the file extracted from zip you copied.

:::image type="content" source="./media/6SourceDevice.png" alt-text="Screenshot of selecting the source device for database restore.":::

1. Select **Options**, and then select **Overwrite the existing database** and **Close existing connections to destination database**.
1. Select **OK**.

:::image type="content" source="./media/7RestoreSetting.png" alt-text="Screenshot of the restore settings options dialog.":::

You will receive confirmation that the AXDB restore was successful. After you receive this confirmation, you can close SQL Services Management Studio.

1. Go back to **Internet Information Services** > **Application Pools** > **AOSService** and start the AOSService.
1. Go to **Services** and start the two services you stopped earlier.

1. Locate the AdminUserProvisioning tool on this VM. Look under, K:\AosService\PackagesLocalDirectory\bin\AdminUserProvisioning.exe.
1. Run the .ext file using your user address in the **Email Address** field.
1. Select **Submit**.

:::image type="content" source="./media/8AdminUserProvisioning.png" alt-text="Screenshot of the Admin User Provisioning tool dialog.":::

This takes a couple of minutes to complete. You should receive a confirmation message that the Admin user was successfully updated.

1. Lastly, run Command Prompt as Administrator and perform iisreset

:::image type="content" source="./media/9IISReset.png" alt-text="Screenshot of running iisreset command in Command Prompt.":::

1. Close the remote desktop session and use the Lifecycle Services **Environment details** page to log in to the environment to confirm it is working as expected.

:::image type="content" source="./media/10FinanceAndOperations.png" alt-text="Screenshot of the Finance and Operations application after successful setup.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
