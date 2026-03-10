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

The Resource Requirement, Resource Requirement Detail, and Bookable Resource Booking entities now support time zone agnostic dates, enabling more flexible date handling across different time zones. To support this capability, the new fields are added to all entities.

| Display Name | Field | Entity | Description |
|-------|----------------------|--------------------|-----------------------|
| From Date Time Zone Independent | msdyn_TzaFromDate | Resource Requirement | From date of the resource requirement in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaToDate | Resource Requirement | To date of the resource requirement in time zone independent format |
| From Date Time Zone Independent | msdyn_TzaFrom | Resource Requirement Detail | From date of the resource requirement detail in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaTo | Resource Requirement | To date of the resource requirement detail in time zone independent format |
| Start Date Time Zone Independent | msdyn_TzaStartTime | Bookable Resource Booking | Start date and time of the booking in time zone independent format |
| End Date Time Zone Independent | msdyn_TzaEndTime | Bookable Resource Booking | End date and time of the booking in time zone independent format |

The new time zone agnostic dates are editable. When you edit a time zone dependent date, the corresponding time zone agnostic date is automatically calculated, and vice versa. 

For existing projects, the system calculates time zone agnostic dates by using lazy loading. The system populates them when you open the main form of their respective entity (Resource Requirement, Resource Requirement Detail, or Bookable Resource Booking) for the first time. Until you open the form, these dates are empty in the database.

> [!NOTE]
> Use time zone agnostic dates for reporting and display purposes only. The scheduling engine continues to use the time zone dependent dates for all scheduling calculations and operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
