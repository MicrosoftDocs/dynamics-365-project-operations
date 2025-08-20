---
title: Update the Dynamics 365 expense management mobile app 
description: This article explains how to update the Dynamics 365 expense management mobile app.
author: ajitchandran
ms.date: 08/20/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: ajitchandran
ms.custom: 
  - bap-template
---
# Update the Dynamics 365 expense management mobile app 

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how to **update** the Dynamics 365 expense management mobile app to the latest available version. Follow these steps after you installed the Dynamics 365 expense management mobile app and you want update to the latest version. Learn how to install and configure the Dynamics 365 expense management mobile app for your Microsoft Dynamics 365 Finance and Dataverse environment in [Install and configure the Dynamics 365 expense management mobile app](/dynamics365/project-operations/expense/new-expense-mobile-app-install-and-configure).

## Steps to update the Dynamics 365 expense management mobile app

To ensure you're using the latest features and improvements, use the following steps to update the Dynamics 365 Expense Management mobile app.

### Step 1: Update your finance and operations environment

Ensure that your finance and operations environment is updated to the specified patch version or a later one. 

### Step 2: Refresh entities in the finance & operations environment

After updating the environment, refresh all entities. To refresh the entities, follow these steps.

1. Go to **System Administration** > **Workspaces** > **Data Management** or search for Data Management in the search bar.
1. Select **Framework parameters**.
1. In the **Entity settings** section, select **Refresh entity list**. This action triggers a batch job and takes some time to complete. To monitor the progress, go to **System administration** > **Inquiries** > **Batch jobs**, or search for Batch jobs, and locate the job with the description Refresh entity list. 
1. After the job is completed, complete Step 3: Update the expense management mobile app.

### Step 3: Update the expense management mobile app

Complete the process by updating the Expense Management mobile app via the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/).

1. Go to [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/).
1. Select the desired environment in which you want to update the Dynamics 365 Expense Management mobile app.
1. Go to **Dynamics 365 Apps** within the **Resources** section.
1. Search for **Dynamics 365 Expense Management**. The **Update available** option displays when an update for the app is available.
1. Select **Update available** option, and wait for it to complete.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
