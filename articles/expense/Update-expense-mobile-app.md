---
title: Update the Dynamics 365 expense management mobile app 
description: This article explains how to update the Dynamics 365 expense management mobile app.
author: ajitchandran
ms.date: 08/12/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: ajitchandran
ms.custom: 
  - bap-template
---
# Update the Dynamics 365 expense management mobile app

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how to **update** the Dynamics 365 expense management mobile app to the latest available version. This is only when you already have the Dynamics 365 expense management mobile app installed and are looking to update to the latest version. For more information about installing and configuring the Dynamics 365 expense management mobile app for your Microsoft Dynamics 365 Finance and Dataverse environment, see [Install the Power Apps mobile app](/power-apps/mobile/run-powerapps-on-mobile).

To ensure you are using the latest features and improvements, please follow the steps below to update the Dynamics 365 Expense Management mobile app:
Step 1: Update Your Finance & Operations Environment
Ensure that your Finance & Operations environment is updated to the specified patch version or a later one. 

Step 2: Refresh Entities in the Finance & Operations Environment
After updating the environment, refresh all entities by following these instructions:
1.	Navigate to System Administration > Workspaces > Data Management or simply search for Data Management in the search bar.
2.	Select Framework parameters.
3.	Under the Entity settings section, click Refresh entity list.
4.	This action will trigger a batch job. The process may take some time.
5.	To monitor the progress, go to System administration > Inquiries > Batch jobs, or search for Batch jobs, and locate the job with the description Refresh entity list. Once the job is completed, proceed with step 3.

Step 3: Update the Expense Mobile App
Complete the process by updating the Expense Management mobile app via the Power Platform Admin Center (PPAC)
