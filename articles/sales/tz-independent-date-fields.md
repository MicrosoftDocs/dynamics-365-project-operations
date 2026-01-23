---
title: Use time zone independent date fields
description: Learn about time zone independent date fields and their behavior in the context of Project Operations
author: suvaidya
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
- bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Use time zone independent date fields

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

[!INCLUDE[banner](../includes/banner.md)]

The Time Zone Independent Milestone Date feature ensures that milestone dates in the Project contract line milestone entity are consistent and aren't affected by the signed in user's local time zone (TZ). When you enable this feature, it helps improve the billing accuracy of project based milestones.  

## Get started

To enable the Time Zone Independent Milestone Date feature, follow these steps:

1. Go to  **Settings** \> **Parameters** \> **Feature control** \> **Enable TZ Independent Milestone Date**.
1. Update your Dual-write map version to 1.0.0.7 to use the milestone date (TZ independent) date field in your finance and operations apps environment.

## Expected behaviors after enabling the Time Zone Independent Milestone Date feature

The following list shows the expected behaviors after you enable the Time Zone Independent Milestone Date feature.

- All out-of-the-box (OOB) forms and views that currently use the Milestone date are updated to use the TZ Independent Milestone date. The quote line and contract line entities also update.
- Both date values **msdyn_invoicedate** and **msdyn_milestonedate** are set, regardless of the feature flag state.
- You can use the new Dual-write map version with the TZ independent milestone date value on finance and operations apps to sync over the TZ independent milestone date.

## Upgrade impact

The upgrade process updates the Milestone date (TZ independent) value on existing milestones in the quote line and contract line entities when the user triggers an action on a related form or view.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
