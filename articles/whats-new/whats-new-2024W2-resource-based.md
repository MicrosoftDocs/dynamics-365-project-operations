---
title: What's new 2024 Wave 2 early access - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the features available in the 2024 wave 2 early access release of Project Operations resource/non-stocked based scenarios deployment.
author: mohitmenon
ms.custom:
  - evergreen
ms.date: 08/13/2024
ms.reviewer: johnmichalak
ms.topic: article
ms.author: tulsijhaveri
---

# What's new 2024 Wave 2 early access - Project Operations for resource/non-stocked based scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.110.0.10
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.40

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management |**Project Calendar Control** <br><br> Allows users to directly edit a project's calendar on the project form| |
| Sales |**Sales copy with company** <br><br> This feature introduces the capability to select an alternate company when copying Opportunity, Quote, and Project Contract records. With this feature, users gain the flexibility to seamlessly duplicate relevant records across different companies, streamlining the efficient templatizing and re-pathing of opportunities, quotes, and contracts.| |

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Pricing |**Date effective role price override can be easily tracked in price list** <br><br> Previously, users had to expand each role in the price lists view to check for date-effective price overrides. With this new feature, if a role has one or more date-effective price overrides, the total number of overrides will be displayed in an additional column named 'Overrides'. A positive number in the 'Overrides' column indicates that there|  |
| Sales |**Price-override from Quote line details** <br><br> This feature which was previously behind a separate feature flag, will now be available by default. Users can create a role price override directly from quote line details. | |
| Time Entry |**Copilot in time entry** <br><br> Copilot in time entry will be available in regions other than North America, for early access testing. | |
