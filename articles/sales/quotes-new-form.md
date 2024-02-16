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

**Recalculate** must be selected on the quote to update the KPIs.

## Role price override within Quote Line Detail form
The Price Override button, integrated into the Quote Line form, facilitates the modification of price overrides for quote line details. This functionality significantly reduces the number of clicks  and streamlines the process of adjusting prices while maintaining focus within the context of each specific quote line detail.

**Usage Instructions:**
Select the quote line detail that requires price adjustment. Click on the Price Override button to initiate the price modification process. A flyout will appear, allowing you to edit the price while retaining the context of the quote line detail.

**Functionality:**
If an existing price override exists, the system will automatically update it with the new price. In cases where no existing override is present, the system will generate a new price override. The Price Override button will only illuminate only if the price you are editing is sourced from the role price list.

**Additional Details:**
Upon creation, the price override will be assigned a default date effective, aligned with the start date of the Price list. You have the option to specify a different effective date for the price override within the flyout. The scope of the price override will be automatically configured to the respective quote. The scope is not allowed to be changed.

## One Grid: nested Quote Line grid

With the introduction of nested grids, you have the capability to view and edit both quote lines and their corresponding quote line details within a single grid interface. This functionality enhances usability and efficiency by providing a consolidated view of all related information while enabling seamless editing of both quote lines and quote line details. Quote lines are presented with the respective Quote line details with latter being nested within the same grid, eliminating the need to switch between multiple screens or tabs.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
