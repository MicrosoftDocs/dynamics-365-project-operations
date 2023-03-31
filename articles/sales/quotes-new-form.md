---
# required metadata

title: New Quote Form experience
description: This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.
author: stsporen
ms.date: 3/31/2023
ms.topic: conceptual
ms.custom: bap-template
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
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: stsporen
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---
# New Quote Form experience

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.

We're releasing the initial version of our new quote experience. The goal of this feature is to improve the overall user experience, uptake new platform capabilities, and simplify the user interactions when creating a quote. 

Features include:
- New, clean experience with a single form layout.
- New KPI control that highlights key quote metrics.
- Reduced the number of form interactions. 
- Provide scenario-focused data views.

## Usages Changes
We've significantly reduced the number of tabs in the Quote form. Below is a list of the updates and changes, and where to find them.

### Summary Tab
All the related tabs for the quote are moved to the **Summary** tab. The **Summary** tab has all of your form details for the quote, including customer billing details, price lists, timeline, graphs, and KPI’s that highlight the status of the quote.

### Project Lines Tab
The Quote Lines grid is updated to include the new grid capabilities of the platform. These capabilities include the ability to edit line filters, such as time, expense, material, or fee. Selecting the name opens the legacy quote line form.

### Product Lines Tab
The Product Lines tab includes all the product capabilities, allowing you to add product-based quote lines for the project.

### Analytics Tab
This tab is a replica of the out-of-the-box analytics tab, where you can deep dive into the data behind the quote.


## What’s next and is it ready for production?
We'll be releasing monthly updates to this form, some of which will radically change the interface. We recommend using the form but expect it to change with each release as we work to add more features and capabilities.

Our next goal is to improve the grid experience with price editing capabilities, and a nested quote line detail grid.
We'll update this document with notes and progress as this process completes.

## Known Issues
- Required to press "Recalculate" on the quote to update the KPIs.
- Nested grid for Quote Line Details not available.

## How to enable and disable the new Quote form experience

To enable and disable the new Quote form experience, follow these steps.

1. As a user with system customizer privileges, open [https://make.powerapps.com](https://make.powerapps.com).
1. From the environment picker, select the correct environment.
1. Select **Solutions** and **Project Operations** (name: ProjectService).
1. Select **Edit**.
1. Expand **Tables**, **Quote**, and then **Forms**.
1. Enable or disable the form:
   - To enable the new form, select **Project Quote Information**, and select **Turn On**. 
   - To disable the new form and enable the old form, select **Project Information**, and select **Turn Off**.
   - [Optionally] You can leave both forms enabled, allowing you to switch between experiences.
1. On the left, select **<- Back to solutions**.
1. Select **Publish all customizations** to update the environment with the changes.

If you want to revert to your original form, turn on **Project Information** and turning off **Project Quote Information**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
