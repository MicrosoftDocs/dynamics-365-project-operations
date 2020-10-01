---
title: Apply demo setup and configuration data
description: 
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Apply demo setup and configuration data 

_**Lite deployment - deal to proforma invoicing_

# Apply demo setup and configuration data for Project Operations lite deployment

1. Download the Master Data Package [here](https://download.microsoft.com/download/3/4/1/341bf279-a64f-4baa-af31-ce624859b518/ProjOpsSampleSetupData%20-%20CE%20only%20CMT.zip). (https://download.microsoft.com/download/3/4/1/341bf279-a64f-4baa-af31-ce624859b518/ProjOpsSampleSetupData%20-%20CE%20only%20CMT.zip)
2. Navigate to the folder &quot;ProjOpsDemoDataSetupAndMaster - Integrated CMT&quot; and run the executable file called &quot;DataMigrationUtility&quot;.
3. On page 1 of the CMT Wizard, Select the Import Data option and hit &quot;Continue&quot;

![Configuration Migration](1ConfigurationMigration.png)

1. On Page 2 of the CMT Wizard, select Office 365 as the &quot;Deployment Type&quot;, select to &quot;Display a list of available organizations&quot; and &quot;Show Advanced&quot;.

Select the region of your tenant, put in your credentials, and click on &quot;Login&quot;

![Configuration Sign in](2ConfigurationSignin.png)

1. On the next page 3 of the CMT wizard, you will be shown a list of Organizations on the Tenant. Select the Organization into which you would like to import the demo data and click on Login.
2. On the next page 4 of the CMT wizard, select the zip file called &quot;MasterAndSetupData&quot; from the unpacked folder &quot;ProjOpsDemoDataSetupAndMaster - Integrated CMT&quot;

![Zip file](3ZipFile.png)

![Select a file](4SelectAFile.png)

1. Once the zip file is selected, the Import Data button lights up. Click on the &quot;Import Data&quot; button on the CMT Wizard.

![Import data](5ImportData.png)

1. Import will run for approximately 2-10 minutes depending on your network speed. Once it completes, exit the CMT Wizard. Check your Org for data in the 20 entities listed below:

1. Currency
2. Organizational Unit
3. Contact
4. Tax Group
5. Customer Group
6. Unit
7. Unit Group
8. Price List
9. Project Parameter Price List
10. Invoice Frequency
11. Invoice Frequency Detail
12. Bookable Resource Category
13. Transaction Category
14. Expense Category
15. Role Price
16. Transaction Category Price
17. Characteristic
18. Bookable Resource
19. Bookable resource category Assn
20. Bookable Resource Characteristic

![Complete Import](6CompleteImport.png)
