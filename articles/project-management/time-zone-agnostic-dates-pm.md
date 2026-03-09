---
title: Time zone agnostic dates in Project and Project Task
description: Learn about time zone agnostic dates in project and project task
author: dishantpopli
ms.date: 03/09/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Time zone agnostic dates in Project and Project Task

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Project and Project Task entities now support time zone agnostic (TZA) dates, enabling more flexible date handling across different time zones. To support this capability, the system adds new fields to both entities.

| Display Name | Field | Entity | Description |
|-------|----------------------|--------------------|-----------------------|
| Start Date Time Zone Agnostic | msdyn_tzascheduledstart | Project | Start date of the project (Time Zone Agnostic) |
| Finish Date Time Zone Agnostic | msdyn_tzafinish | Project | Finish date of the project (Time Zone Agnostic) |
| Start Date Time Zone Agnostic | msdyn_tzascheduledstart | Project Task | Scheduled start time of the project task (Time Zone Agnostic) |
| Due Date Time Zone Agnostic | msdyn_tzascheduledend | Project Task | Scheduled end time of the project task (Time Zone Agnostic) |

## Project entity

The new TZA fields on the Project entity are editable, so you can update project schedules using either TZA or non-TZA date fields. When you edit a non-TZA date, the system automatically calculates the corresponding TZA date, and vice versa.

## Project Task entity

The new TZA fields on the Project Task entity are read-only. You must update the non-TZA date fields directly, and the system automatically calculates the TZA fields.  

For existing projects, the system uses lazy loading to calculate TZA field values. The system populates TZA fields when you open the project main form for the first time. Until you open the form, these fields are empty in the database.

## How time zone conversion works

The system automatically converts non-TZA dates to TZA dates by using the **project calendar's time zone** as the reference.

### With TZA fields (new)

The system displays dates based on the project calendar's time zone, so all users see consistent dates.

### With non-TZA fields (previous)

The system converts UTC to each user's individual time zone (set in personalization settings), so different users see different dates and times for the same project data.

> [!NOTE]
> Automatic conversion to TZA dates uses the working hours from the project calendar. Ensure your project calendar has the correct working hours configured for accurate results.
>
> Use TZA fields for reporting and display purposes only. The scheduling engine continues to use the non-TZA fields for all scheduling calculations and operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
