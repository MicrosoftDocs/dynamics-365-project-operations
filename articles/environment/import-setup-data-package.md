---
title: Import the Setup data package
description: Learn how to prepare, run, and validate the import of the PD - PO Core - Setup Data package into a Dynamics 365 environment using Package Deployer.
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
ms.reviewer: johnmichalak
ms.date: 09/17/2026
---

# Import the setup data package

[!INCLUDE [banner](../includes/banner.md)]

This article shows you how to import the **PD - PO Core - Setup Data** package into your Dynamics 365 environment by using Package Deployer, and how to confirm that the import succeeded. Import the setup data package before the transactional data package, because the transactional records depend on records this package creates. Complete the steps in this article before you move on to importing the transactional data package.

Before you begin, ensure you complete the steps in [Prerequisites for core package import](data-package-prerequisites.md).

## Prepare the package files

1. Download the [PD - PO Core - Setup Data](https://download.microsoft.com/download/a518f4e3-316a-4ee4-bfea-5180c96d1122/PD%20-%20PO%20Core%20-%20Setup%20Data%20%281%29.zip) package to your computer, and wait until the download finishes completely.
1. Right-click the downloaded zip file and select **Properties**. On the **General** tab, select the **Unblock** checkbox near the bottom-right (next to **Security**), then select **Apply** and **OK**.

   > [!IMPORTANT]
   > Windows blocks files you download from the internet. If you skip this step, Package Deployer might report that no packages were found.

1. Right-click the file again and select **Extract All**, choose a destination, and select **Extract**.
1. Open the extracted folder, then open the **PD - PO Core - Setup Data** folder inside it.

## Run Package Deployer

1. Locate **PackageDeployer** and double-click it. When the **Package Deployer for Microsoft Power Platform** window opens, select **Continue**.
1. On the **Connect to Microsoft Power Platform** screen, set **Deployment Type** to **Office 365**, select **Show Advanced**, enter valid credentials, and select **Login**.
1. Enter the full Dynamics 365 instance URL when prompted, then select **OK**.

   :::image type="content" source="media/core-package-connect-power-platform.png" alt-text="Screenshot of the Connect to Microsoft Power Platform window with Office 365 selected, Show Advanced checked, credentials entered, and Login highlighted.":::

1. On the **Welcome** screen, select **Next**. On the **Ready to Install** screen, confirm that the solution package and organization are correct, then select **Next**.
1. Package Deployer reads the configuration file and validates readiness. When every validation item shows a green check mark, select **Next** to start the import.

   :::image type="content" source="media/core-package-setup-data-installer.png" alt-text="Screenshot of the installer configuration validation screen listing import configuration, solution, and connection thread messages.":::

1. Wait for the import to run. When it finishes, the screen shows **Import Process Completed** and each step has a green check mark. Select **Next**.

   :::image type="content" source="media/core-package-install-actions.png" alt-text="Screenshot of the Executing Install Actions screen with Import Process completed and Next highlighted.":::

1. On the **Installation Completed** screen, select **Finish**. The **PD - PO Core - Setup Data** package is now imported.

## Common issues

If Package Deployer reports that no import packages were found, confirm that the download finished completely and that you unblocked the file. Then, import the package again.

## Validate the Setup data

1. Sign in to the organization and open the Project Operations app.
1. Go to **Sales** > **Price Lists** and select the **Active Price Lists** view.
1. Confirm that the record count at the bottom-left shows **13** rows, and that the **End Date** is in the year **2035**.

   :::image type="content" source="media/core-package-active-price-list.png" alt-text="Screenshot of the Active Price Lists view in Project Operations showing 13 rows with Name, Currency, Start Date, and End Date columns.":::

If the record count and end date match, the setup data package imported correctly. You're ready to import the transactional records. 

## Next steps

Continue with [Import the transactional data package](import-transactional-data-package.md).
