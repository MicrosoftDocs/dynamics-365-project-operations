---
title: Time zone agnostic dates in Resource Management
description: Learn about time zone agnostic dates in resource management entities.
author: dishantpopli
ms.date: 03/09/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Time zone agnostic dates in resource management

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Resource Requirement, Resource Requirement Detail, and Bookable Resource Booking entities now support time zone agnostic (TZA) dates, enabling more flexible date handling across different time zones. To support this capability, the new fields are added to all entities.

| Display Name | Field | Entity | Description |
|-------|----------------------|--------------------|-----------------------|
| From Date Time Zone Independent | msdyn_TzaFromDate | Resource Requirement | From date of the resource requirement in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaToDate | Resource Requirement | To date of the resource requirement in time zone independent format |
| From Date Time Zone Independent | msdyn_TzaFrom | Resource Requirement Detail | From date of the resource requirement detail in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaTo | Resource Requirement | To date of the resource requirement detail in time zone independent format |
| Start Date Time Zone Independent | msdyn_TzaStartTime | Bookable Resource Booking | Start date and time of the booking in time zone independent format |
| End Date Time Zone Independent | msdyn_TzaEndTime | Bookable Resource Booking | End date and time of the booking in time zone independent format |

The new TZA fields are editable, so you can update either TZA or non-TZA date fields. When you edit a non-TZA date, the corresponding TZA date is automatically calculated, and vice versa. 

For existing projects, the system calculates TZA field values by using lazy loading. The system populates TZA fields when you open the main form of their respective entity (Resource Requirement, Resource Requirement Detail, or Bookable Resource Booking) for the first time. Until you open the form, these fields are empty in the database.

> [!NOTE]
> Use TZA fields for reporting and display purposes only. The scheduling engine continues to use the non-TZA fields for all scheduling calculations and operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
