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

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how to **update** the Dynamics 365 expense management mobile app to the latest available version. Use this feature after you already installed the Dynamics 365 expense management mobile app and you want update to the latest version. To install and configure the Dynamics 365 expense management mobile app for your Microsoft Dynamics 365 Finance and Dataverse environment, learn more in [Install and configure the Dynamics 365 expense management mobile app](/dynamics365/project-operations/expense/new-expense-mobile-app-install-and-configure).

## Steps to update the Dynamics 365 expense management mobile app

To ensure you're using the latest features and improvements, use the following steps to update the Dynamics 365 Expense Management mobile app:

### Step 1: Update your finance & operations environment

Ensure that your Finance & Operations environment is updated to the specified patch version or a later one. 

### Step 2: Refresh entities in the finance & operations environment

After updating the environment, refresh all entities by following these instructions:

1. Navigate to **System Administration** > **Workspaces** > **Data Management** or simply search for Data Management in the search bar.
1. Select **Framework parameters**.
1. Under the **Entity settings** section, **Refresh entity list**.
1. This action triggers a batch job. The process takes some time.
1. To monitor the progress, go to **System administration** > **Inquiries** > **Batch jobs**, or search for Batch jobs, and locate the job with the description Refresh entity list. Once the job is completed, proceed with step 3.

### Step 3: Update the expense management mobile app

Complete the process by updating the Expense Management mobile app via the [Power Platform Admin Center (PPAC)](https://admin.powerplatform.microsoft.com/)

1. Goto [Power Platform Admin Center (PPAC)](https://admin.powerplatform.microsoft.com/)
1. Select the desired environment in which you want to update the Dynamics 365 Expense Management mobile app.
1. Go to Dynamics 365 Apps within the Resources section.
1. Search for **Dynamics 365 Expense Management** and the **Update available** option displays when an update is available.
1. Select the **Update available** option and wait for it to complete.
