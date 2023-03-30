---
# required metadata

title: New Quote Form experience
description: This article provides information about the updates applies to the project quotes form in Microsoft Dynamics 365 Project Operations.
author: stsporen
ms.date: 3/29/2023
ms.topic: article
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: stsporen
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---
# New Quote Form experience

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

We are releasing the initial version of our new quote experience. The goal of this feature is to improve the overall user experience, uptake new platform capabilities and simplify the user interactions when creating a quote. 

Features include:
- New clean experience with a single form layout.
- New KPI control for highlights key quote metrics.
- Reduced the number of form interactions. 
- Scenario focused data views.

## Usages Changes
We have significantly reduced the number of tabs in the Quote form. Below is a list of the updates and changes and where to find them in the new set.

### Summary Tab
We have moved all the related tabs for the quote under a single tab, listed as the Summary tab. Here you will find all your form details around the quote, including customer billing details, price lists, timeline, graphs and KPI’s to highlight the status of the quote.

### Project Lines Tab
We have upgrades the Quote Lines gris to uptake the new grid capabilities of the platform, this includes the ability to edit line filters such as time, expense, material, or fee. Selecting the name will open the legacy quote line form.

### Product Lines Tab
The Product Lines tab includes all the product capabilities, allowing you to add product-based quote lines for the project.

### Analytics Tab
This tab is a replica of the OOB analytics tab, where you can deep dive into the data behind the quote.



## What’s next and is it ready for production?
We will be releasing monthly updates to this form, some of which will radically change the interface. We recommend using the form but expect it to change with each release as we work to add more features and capabilities.

Our next goal is to improve the grid experience with price editing capabilities and a nested quote line detail grid.
We will update this document with notes and progress as this process completes.

## Known Issues
- Required to press "Recalculate" on the quote to update the KPI’s.
- Nested grid for Quote Line Details not available.

## How to enable and disable the new Quote form experience
1.	As a user with system customizer privileges open https://make.powerapps.com.
2.	Be sure to switch to the correct environment in the top right environment picker .
3.	Select **Solutions** and **Project Operations** (name: ProjectService).
4.	Press **Edit**.
5.	Expand **Tables** and then **Quote** and **Forms**.
6.	Select **Project Quote Information** and press **Turn On**. This will enable the new form.
7.	Select **Project Information** and press **Turn Off**. This will disable the old form.
8.	[Optionally] You can leave both forms enabled, allowing you to switch between experiences .
9.	On the left select **<- Back to solutions**.
10.	Press **Publish all customizations** to update the environment with the changes.
11.	Swap the forms back by turning on **Project Information** and turning off **Project Quote Information** if you wish to revert to your original form.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
