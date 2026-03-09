---
title: Time zone agnostic dates in Resource Management
description: Learn about time zone agonsitc dates in resource requirement, resource requirement detail, bookable resource booking and bookable resource booking header.
author: dishantpopli
ms.date: 02/20/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Time Zone Agnostic Dates in Resource Management

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Resource Requirement, Resource Requirement Detail. Bookable Resource Booking and Bookable Resource Booking Header entities now support time zone agnostic (TZA) dates, enabling more flexible date handling across different time zones. To support this capability, new fields have been introduced to all entities.

| Display Name | Field | Entity | Description |
|-------|----------------------|--------------------|-----------------------|
| From Date Time Zone Independent | msdyn_TzaFromDate | Resoure Requirement | From date of the resource requirement in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaToDate | Resoure Requirement | To date of the resource requirement in time zone independent format |
| From Date Time Zone Independent | msdyn_TzaFrom | Resoure Requirement Detail | From date resource requirement detail in time zone independent format |
| To Date Time Zone Independent | msdyn_TzaTo | Resoure Requirement | To date resource requirement detail in time zone independent format |
| Start Date Time Zone Independent | msdyn_TzaStartTime | Bookable Resource Booking | Start date and time of the booking in time zone independent format |
| End Date Time Zone Independent | msdyn_TzaEndTime | Bookable Resource Booking | End date and time of the booking in time zone independent format |
| Start Date Time Zone Independent | msdyn_TzaStartTime | Bookable Resource Booking Header | Start date and time of the booking summary in time zone independent format |
| End Date Time Zone Independent | msdyn_TzaEndTime | Bookable Resource Booking Header | End date and time of the booking summary in time zone independent format |

The new TZA fields on the Project entity are editable, allowing you to update project schedules using either TZA or non-TZA date fields. When you edit a non-TZA date, the corresponding TZA date is automatically calculated, and vice versa. 

## How time zone conversion works
The system automatically converts non-TZA dates to TZA dates using the **project calendar's time zone** as the reference.

**With TZA fields (new):**
Dates are converted and displayed based on the project calendar's time zone, ensuring consistency across all users.

**With non-TZA fields (previous):**
The system converted UTC to each user's individual time zone (set in personalization settings), resulting in different users seeing different dates and times for the same project data.

> [!NOTE]
> Automatic conversion to TZA dates uses the working hours from the project calendar. Ensure your project calendar has the correct working hours configured for accurate results.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
