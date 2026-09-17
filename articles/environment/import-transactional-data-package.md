---
title: Import the Transactional data package
description: Learn how to prepare, run, and validate the import of the PD - PO Core - Transactional Data package into a Dynamics 365 environment using Package Deployer.
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
ms.reviewer: johnmichalak
ms.date: 09/17/2026
---

# Import the transactional data package

[!INCLUDE [banner](../includes/banner.md)]

This article shows you how to import the **PD - PO Core - Transactional Data** package into your Dynamics 365 environment by using Package Deployer, and how to confirm that the import succeeded.

> [!IMPORTANT]
> Import the **PD - PO Core - Setup Data** package before you import the transactional data package. The transactional records depend on records the setup data package creates, and importing out of order causes the import to fail. If you didn't import the setup data package yet, see [Import the Setup data package](import-setup-data-package.md).

This demonstration data is for evaluation purposes only. Deploy it to a non-production Dynamics 365 environment.

## Prepare the package files

1. Download the [PD - PO Core - Transactional Data](https://download.microsoft.com/download/b3be8632-88f3-4b06-bd09-3a1e9afeb33c/PD%20-%20PO%20Core%20-%20Transactional%20Data%20%281%29.zip) package to your computer, and wait until the download finishes completely.
1. Right-click the downloaded zip file and select **Properties**. On the **General** tab, select the **Unblock** checkbox, then select **Apply** and **OK**.
1. Right-click the file again and select **Extract All**, choose a destination, and select **Extract**.
1. Open the extracted folder, then open the **PD - PO Core - Transactional Data** folder inside it.

## Run Package Deployer

1. Double-click **PackageDeployer**, and then select **Continue** when the Package Deployer window opens.
1. On the **Connect to Microsoft Power Platform** screen, set **Deployment Type** to **Office 365**, select **Show Advanced**, enter your credentials, and select **Login**. Enter the full Dynamics 365 instance URL when prompted, then select **OK**.

   :::image type="content" source="media/core-package-deployer.png" alt-text="Screenshot of Package Deployer's Connect to Microsoft Power Platform screen with Office 365 selected, Show Advanced checked, credentials entered, and Login highlighted.":::

1. On the **Welcome** screen, select **Next**. On the **Ready to Install** screen, confirm that the solution package and organization are correct, then select **Next**.
1. Package Deployer reads the configuration file and validates readiness. When every validation item shows a green check mark, select **Next** to start the import.
1. Wait for the import to run. When it finishes, the screen shows **Import Process Completed** with a green check mark on each step. Select **Next**.
1. On the **Installation Completed** screen, select **Finish**. The **PD - PO Core - Transactional Data** package is now imported.

## Common issues

If Package Deployer reports a pre-import step failure, rerun the import starting from the **PackageDeployer** step. The tool detects what's missing and completes it on the rerun, so repeat this rerun until the import finishes successfully.

:::image type="content" source="media/core-package-import-install-actions.png" alt-text="Screenshot of Package Deployer Executing Install Actions screen with a pre-import process failure error.":::

If Package Deployer reports that no import packages were found, confirm that the download finished completely and that you unblocked the file, then import the package again.

## Validate the transactional data

1. Sign in to the organization and open the Project Operations app.
1. Go to **Projects** > **Projects** and select the **All Active Projects** view.
1. Confirm that the record count at the bottom-left shows **14** rows, and that the **Effort (Hours)** and **Estimated Total Cost** columns contain values for each project.

   :::image type="content" source="media/core-package-all-active-projects.png" alt-text="Screenshot of the All Active Projects view in Project Operations with Effort (Hours) and Estimated Total Cost columns and 14 rows highlighted.":::

If the record count and column values match, the transactional data package imported correctly. Your environment now has the Project Operations demonstration data installed and ready to use.

## Related information

[Project Operations Core - End-to-end Sample Demo Script](https://download.microsoft.com/download/dcbed4da-9e4f-44df-a184-77bcba048e21/D365-PO-Core-E2E-Flow.pdf)
