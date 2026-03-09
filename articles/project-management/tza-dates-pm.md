---
title: Time zone agnostic dates in Project and Project Task
description: Learn about time zone agonsitc dates in project and project task
author: dishantpopli
ms.date: 02/20/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Time Zone Agnostic Dates in Project and Project Task

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Project and Project Task entities now support time zone agnostic (TZA) dates, enabling more flexible date handling across different time zones. To support this capability, new fields are added to both entities.

| Display Name | Field | Entity | Description |
|-------|----------------------|--------------------|-----------------------|
| Start Date Time Zone Agnostic | msdyn_tzascheduledstart | Project | Start date of the project (Time Zone Agnostic) |
| Finish Date Time Zone Agnostic | msdyn_tzafinish | Project | Finish date of the project (Time Zone Agnostic) |
| Start Date Time Zone Agnostic | msdyn_tzascheduledstart | Project Task | Scheduled start time of the project task (Time Zone Agnostic) |
| Due Date Time Zone Agnostic | msdyn_tzascheduledend | Project Task | Scheduled end time of the project task (Time Zone Agnostic) |

**Project Entity:**
The new TZA fields on the Project entity are editable, allowing you to update project schedules using either TZA or non-TZA date fields. When you edit a non-TZA date, the corresponding TZA date is automatically calculated, and vice versa.

**Project Task Entity:**
The new TZA fields on the Project Task entity are read-only. You must update the non-TZA date fields directly, and the TZA fields are calculated automatically. 

## How time zone conversion works
The system automatically converts non-TZA dates to TZA dates using the **project calendar's time zone** as the reference.

**With TZA fields (new):**
Dates are displayed based on the project calendar's time zone, ensuring consistency across all users.

**With non-TZA fields (previous):**
The system converted UTC to each user's individual time zone (set in personalization settings), resulting in different users seeing different dates and times for the same project data.

> [!NOTE]
> Automatic conversion to TZA dates uses the working hours from the project calendar. Ensure your project calendar has the correct working hours configured for accurate results.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
