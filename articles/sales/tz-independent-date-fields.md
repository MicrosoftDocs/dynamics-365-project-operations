---
title: Use time zone independent date fields
description: Learn about time zone independent date fields and their behavior in the context of Project Operations
author: suvaidya
ms.date: 03/26/2025
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Use time zone independent date fields

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

[!INCLUDE[banner](../includes/banner.md)]

The Time Zone Independent Milestone Date feature ensures that milestone dates in the Project contract line milestone entity are consistent and not affected by the logged in user's local time zone (TZ). Enabling this feature helps improve billing accuracy of project based milestones.  

## Get started

To enable the Time Zone Independent Milestone Date feature, follow these steps.

1. Go to  **Settings** \> **Parameters** \> **Feature control** \> **Enable TZ Independent Milestone Date**. 
2. Update your Dual-write map version to 1.0.0.7 to use the milestone date (TZ independent) date field in your finance and operations apps environment.


## Expected behaviors after enabling the Time Zone Independent Milestone Date feature 

The following list shows the expected behaviors after you enable the Time Zone Independent Milestone Date feature.

- All out-of-the-box (OOB) forms and views currently using the Milestone date are updated with the TZ Independent Milestone date. Quote line and contract line entities are also updated.
- Both date values **msdyn_invoicedate** and **msdyn_milestonedate** are set, irrespective of the feature flag state.
- New Dual-write map version with TZ independent milestone date value can be used on finance and operations apps to sync over TZ independent milestone date. 

## Upgrade impact

The Milestone date (TZ independent) value is updated on existing milestones in the quote line and contract line entities when the user triggers an action on a related form or view. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
