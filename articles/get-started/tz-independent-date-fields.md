---
title: Time Zone Independent Date Fields
description: Learn about time zone independent date fields and their behavior in the context of Project Operations
author: suvaidya
ms.date: 03/26/2025
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Overview of time zone independent Milestone Date

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

[!INCLUDE[banner](../includes/banner.md)]

The Time Zone Independent Milestone Date feature ensures that milestone dates in the Project contract line milestone entity are consistent and not affected by the logged in user's local time zone, thereby improving billing accuracy of project based milestones.  

In resource deployments, the msdyn_invoicedate field in the Project contract line milestone entity uses the user's local time, while the msdyn_invoicedate field in the invoice entity is time zone independent. This discrepancy can cause confusion in cases when the milestone date and the invoice created date are the same, due to the logical name being same across the two entities . The Time Zone Independent Milestone Date feature resolves this issue by ensuring that milestone dates are consistent across all entities.


## Getting Started
To enable the Time Zone Independent Milestone Date feature, follow these steps:

1. Enable feature flag : Navigate to  **Settings** \> **Parameters** \> **Feature control** \> **Enable TZ Independent Milestone Date** 
2. Update Mapping: Use DW map version ... to use the accounting date (TZ independent ) date field in your F&O environment.


## Expected behavior on Enabling Feature Flag

1. All OOB forms and views currently using the Milestone date are updated with the TZ Independent Milestone date . This includes quote line and contract line entities.
2. Both date values **msdyn_invoicedate** and **msdyn_milestonedate** are set, irrespective of the feature flag state.
3. New DW map version with TZ independent milestone date value can be used on F&O to sync over TZ independent milestone date. 

## Upgrade Impact
Milestone date (TZ independent ) date value will be updated on existing milestones in the quote line and contract line entities when the user triggers an action on a related form or view. 
