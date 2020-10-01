---
title: Apply CE setup and configuration data 
description: 
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Apply CE setup and configuration data

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

|
 |
| --- |

## Install CE Setup and Configuration Data

1. Download, unblock and unzip the Setup and Configuration Data Package at [here](https://download.microsoft.com/download/1/3/4/1349369c-6209-42b7-b3b4-5be0e67cacd8/ProjOpsSampleSetupData-%20Integrated%20UR1.zip).
2. Navigate to the unzipped folder and run the executable file called &quot;DataMigrationUtility&quot;.
3. On page 1 of the CMT Wizard, Select the Import Data option and hit &quot;Continue&quot;

![Configuration Migration](1ConfigurationMigration.png)

1. On Page 2 of the CMT Wizard, select Office 365 as the &quot;Deployment Type&quot;, select to &quot;Display a list of available organizations&quot; and &quot;Show Advanced&quot;.

Select the region of your tenant, put in your credentials, and click on &quot;Login&quot;

![Configuration Sign in](2ConfigurationSignin.png)

1. On the next page 3 of the CMT wizard, you will be shown a list of Organizations on the Tenant. Select the Organization into which you would like to import the demo data and click on Login.
2. On the next page 4 of the CMT wizard, select the zip file called &quot;SampleSetupAndConfigData&quot; from the unpacked folder.

![Zip File Selection](3ZipFile.png)

![Select a file](4SelectAFile.png)

1. Once the zip file is selected, the Import Data button lights up. Click on the &quot;Import Data&quot; button on the CMT Wizard.

![Import Data](5ImportData.png)

1. Import will run for approximately 2-10 minutes depending on your network speed. Once it completes, exit the CMT Wizard. Check your Org for data in the 19 entities listed below:

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
11. Bookable Resource Category
12. Transaction Category
13. Expense Category
14. Role Price
15. Transaction Category Price
16. Characteristic
17. Bookable Resource
18. Bookable resource category Assn
19. Bookable Resource Characteristic

![Complete Import](6CompleteImport.png)

|
## Update Project Operations configurations

Navigate to CE environment. You can find it by opening [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments), selecting the environment and selecting Open Environment button on the top of the page. 
![Open Environment](7OpenEnvironment.png)

First, we will create a bookable resource for your user in Projects \&gt; Resources \&gt; New 
![Bookable Resources](8BookableResources.png)

Select your admin user in General tab. Make sure the Time Zone matches the one you are in. 
![New Bookable Resource](9NewBookableResource.png)

In Scheduling tab Company field pick USPM company and click save. 
![Scheduling Tab](10SchedulingTab.png)

Next, select work hours tab. 
![Work Hours](11WorkHours.png)

Double click on any value in the calendar. Select Edit-\&gt;&quot;all events in the series&quot; 
![Work Calendar](12WorkCalendar.png)

Change work hours to 8 hrs work day, mark weekends as not work days and make sure time zone is matching yours. Save and close. 
![Update Calendar](13UpdateCalendar.png)

Go to Settings \&gt; Calendar templates and create New.
 ![Calendar Templates](14CalendarTemplates.png)
 
 Give it a name, select the Template resource created in the previous steps and click Save 
 ![Save Calendar Template](15SaveCalendarTemplate.png)
 
 As a next step, navigate to Parameters and double click on the record to get to the details: 
 ![Project Parameters](16ProjectParameters.png)
 
Update the following:
- Default company – USPM
- Default Organizational Unit – Contoso Robotics Global
- Invoice Frequency – 7th and Last day
- Work hour template – change to the one created in the previous steps
Click Save. 

![Updated Project Parameters](17UpdatedProjectParameters.png)

 |
| --- |

1
