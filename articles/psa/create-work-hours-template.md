---
title: Create a work hours template
description: This article describes how to create a work hours template in Project Service.
author: ruhercul
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: how-to
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---
# Create a work hours template (Project Service)

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-1x-2x](../includes/cc-applies-to-psa-app-3x.md)]

To create and manage a project, you must apply a calendar template to the project. The calendar template defines the following project attributes:

- Working hours, including start and end time
- Working days
- Calendar exceptions such as non-working days

The calendar template that's applied to a project is a copy of the calendar template defined in your organization’s settings.

> [!NOTE]
> If you change the calendar template, those changes don't propagate to the working hours of the project. To change the working hours of the project, a new template must be applied.

To create a calendar template for your organization, there are two key requirements:

- Define the desired working hours of the template using a new or existing bookable resource.
- Create a new calendar template and associate the template with the bookable resource.

**Define the working hours of the template**

1. Go to **Resources** \> **Resources**.
2. Create a new resource to reference in the calendar template, or select an existing resource.
3. Select the **Work Hours** tab of the resource and complete the instructions in [Set work hours for a resource](/dynamics365/field-service/set-work-hours-resource) to configure the calendar rules.

**Create a new calendar template**

1. Go to **Settings** \> **Calendar Template**.
2. Select **New**, and enter a name, description, and template resource.


> [!NOTE]
> When a resource is referenced in a calendar template, a copy of the resource’s calendar is associated with the calendar template. If the working hours of the copied template change, those changes will not propagate to the calendar template.


### See Also  
 [Set up resources](../psa/set-up-resources.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
