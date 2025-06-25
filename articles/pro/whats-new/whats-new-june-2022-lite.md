---
title: What's new June 2022 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the June 2022 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: sigitac
---

# What's new June 2022 - Project Operations lite deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.43.0.77 or 4.43.0.119

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Subcontracting | 2708885 | Fixed the error message that appears when a user creates a bookable resource booking header record where no bookable resource is filled in. |
| Project planning and tracking | 2629441 | Corrected the workflow triggering logic to help prevent an infinite loop when project tasks are updated. |
| Time and expense | 2641209 | Time entry imports from assignments/bookings must retain a bookable resource reference. |
| Project planning and tracking | 2651148 | The project document header must be guarded.|
| Project planning and tracking | 2653145 | Added validations to ensure that a project record can't be created that has non-valid characters in its name. |
| Time and expense | 2654710 | Corrected the filtering on the **Approvals** page. |
| Billing and pricing | 2667805 | Added validations to help prevent billed sale actuals from being created if backing unbilled sales actuals don't exist. |
| Billing and pricing | 2668378 | Added validations to help prevent a custom pricing dimension from being added unless a logical name and a field name are filled in. |
| Time and expense | 2700428 | Improved the approvals logic to ensure that other approval sets for the project can be processed even if one of the approval sets is stuck in system jobs. |
