---
title: What's new June 2022 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the June 2022 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: sigitac
ms.date: 06/03/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new June 2022 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.43.0.77

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Subcontracting | 2708885 | Fixed error message thrown when user creates a bookable resource booking header record with no bookable resource filled in. |
| Project planning and tracking | 2629441 | Corrected workflow triggering logic to avoid infinte loop when updating project task.|
| Time and expense| 2641209 | Time Entries Import from Assignments/Bookings must retain Bookable Resource reference. |
| Project planning and tracking | 2651148 | Project Document Header must be guarded.  |
| Project planning and tracking | 2653145 | Added validations to ensure a project record cannot be created with invalid characters in it's name |
| Time and expense | 2654710 | Corrected filtering on Approvals form|
| Billing and pricing | 2667805 | Added validations to prevent creating billed sale actuals when backing unbilled sales actuals do not exist|
| Billing and pricing | 2668378 | Added validations to prevent adding custom pricing dimension without filling in logical name and field name |
| Time and expense | 2700428 | Improved approvals logic, ensuring other approval sets for the project can be processed, even if one of the approval sets is stuck in system jobs. |
