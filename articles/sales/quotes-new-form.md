---
# required metadata

title: New Quote form experience
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
# New Quote form experience

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.

We're releasing the initial version of our new quote experience. The goal is to improve the overall user experience, uptake new platform capabilities, and simplify user interactions when a quote is created.

Here are some of the features:

- A new, clean experience that uses a single form layout
- A new key performance indicator (KPI) control that highlights key quote metrics
- A reduction in the number of form interactions
- Scenario-focused data views

## Usage changes

We've significantly reduced the number of tabs in the **Quote** form. This section describes the changes and where to find them.

### Summary tab

All the related tabs for the quote are moved to the **Summary** tab. This tab has all your form details for the quote, including customer billing details, price lists, timeline, graphs, and KPIs that highlight the status of the quote.

### Project Lines tab

The **Quote Lines** grid is updated to include the new grid capabilities of the platform. These capabilities include the ability to edit line filters, such as time, expense, material, or fee. When you select the name, the legacy quote line form is opened.

### Product Lines tab

The **Product Lines** tab includes all the product capabilities, so that you can add product-based quote lines for the project.

### Analytics tab

The **Analytics** tab is a replica of the out-of-box **Analytics** tab, where you can do a deep dive into the data behind the quote.

## What's next and is it ready for production?

We'll be releasing monthly updates to this form. Some of the updates will drastically change the interface. We recommend that you use the form, but you should expect it to change in each release as we work to add more features and capabilities.

Our next goal is to improve the grid experience by adding price editing capabilities and a nested grid for quote line details.

As this process is completed, we'll update this article with notes and progress information.

## Known issues

- **Recalculate** must be selected on the quote to update the KPIs.
- A nested grid for quote line details isn't available.

## Enable and disable the new Quote form experience

To enable and disable the new **Quote** form experience, follow these steps.

1. As a user who has system customizer privileges, open the [Power Apps maker portal](https://make.powerapps.com).
1. In the environment picker, select the correct environment.
1. Select **Solutions** and **Project Operations** (name: **ProjectService**).
1. Select **Edit**.
1. Expand **Tables**, **Quote**, and then **Forms**.
1. Enable or disable the new form:

    - To enable the new form, select **Project Quote Information**, and then select **Turn On**.
    - To disable the new form and enable the old form, select **Project Information**, and then select **Turn Off**.
    - Optional: You can leave both forms enabled. In this way, you can switch between experiences.

1. On the left, select **Back to solutions**.
1. Select **Publish all customizations** to update the environment with the changes.

If you ever want to revert to the original form, use the same basic procedure. However, in step 6, turn on **Project Information**, and turn off **Project Quote Information**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
