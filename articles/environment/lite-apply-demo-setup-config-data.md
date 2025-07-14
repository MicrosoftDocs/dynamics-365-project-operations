---
title: Apply demo setup and configuration data - lite
description: This article provides information about how to apply demo setup and configuration data for Project Operations.
author: rumant
ms.author: rumant
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Apply demo setup and configuration data for Project Operations - lite 

[!INCLUDE[banner](../includes/banner.md)]

_**Project Operations Core_



## Prerequisites

Before you begin the configuration, you must have a Dataverse environment provisioned for Dynamics 365 Project Operations.


## Instructions

1. Download the [Setup Data Package](https://download.microsoft.com/download/3/4/1/341bf279-a64f-4baa-af31-ce624859b518/ProjOpsSampleSetupData-%20CE%20only.zip). 
1. Navigate to the folder *ProjOpsSampleSetupData - CE only CMT* and run the executable file, *DataMigrationUtility*.
1. On page 1 of the Common Data Service Configuration Migration (CMT) Wizard, select **Import Data** and then select **Continue**.

    ![Configuration Migration.](./media/1ConfigurationMigration.png)

1. On Page 2 of the CMT Wizard, select **Microsoft 365** as the **Deployment Type**.
1. Select the **Display a list of available organizations** and **Show Advanced** check boxes.
1. Select the region of your tenant, enter your credentials, and then select **Login**.

   ![Configuration Sign in.](./media/2ConfigurationSignin.png)

1. On page 3, from the list of Organizations on the Tenant, select which organization you want to import the demo data into and then select **Login**.
1. On page 4, select the zip file, *SampleSetupAndConfigData* from the unpacked folder, *ProjOpsSampleSetupData - CE only CMT*.

   ![Zip file.](./media/3ZipFile.png)

   ![Select a file.](./media/4SelectAFile.png)

1. After the zip file is selected, select **Import Data**.

   ![Import data.](./media/5ImportData.png)

1. Import will run for approximately two-ten minutes depending on your network speed. After it completes, exit the CMT Wizard. 
1. Check your organization for data in the following 18 entities:

    -	Currency
    -	Account
    -	Organizational Unit
    -	Contact
    -	Unit
    -	Unit Group
    -	Price List
    -	Project Parameter Price List 
    -	Invoice Frequency
    -	Bookable Resource Category
    -	Transaction Category
    -	Expense Category
    -	Role Price
    -	Transaction Category Price
    -	Characteristic
    -	Bookable Resource
    -	Bookable resource category Assn
    -	Bookable Resource Characteristic

    ![Complete Import.](./media/6CompleteImport.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
