---
title: Create a work hours template
description: How to create a work hours template in Project Service
author: ruhercul
manager: kfend
ms.service: project-operations
ms.custom: 
  - dyn365-projectservice
ms.date: 8/03/2018
ms.topic: article
#
#
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
---
# Create a work hours template (Project Service)

[!INCLUDE[cc-applies-to-psa-app-1x-2x](../includes/cc-applies-to-psa-app-3x.md)]

To create and manage a project, a pre-requisite is the application of a
**Calendar template**. The calendar template defines the following attributes of
a project:

-   Working hours, including start time and end time

-   Working days

-   Calendar exceptions (e.g. no working days)

When the **Calendar template** is applied to the project is a copy of the
selected **Calendar template** defined in your organization’s settings.

> Note: If there are changes to the referenced **Calendar template**, those
changes will not propagate to the working hours of the project. To change the
working hours of the project, a new template will need to be applied.

To create **Calendar template** for your organization, there are two key
requirements:

1.  From an existing or new bookable resource, define the desired working hours
    of the template.

2.  Create a new Calendar template and associate the template with the bookable
    resource.

To define the **Work Hours** of a resource:

1.  Navigate to **Resources \> Resources**

2.  Either create a new **Resource** to be referenced in the **Calendar
    template** or select an existing **Resource**.

3.  Select the **Work Hours** tab of the resource

4.  Follow instructions
    [here](https://docs.microsoft.com/en-us/dynamics365/field-service/set-work-hours-resource)
    to configure the calendar rules.

To create a new Calendar template:

1.  Navigate to **Settings \> Calendar Template**

2.  Select **New**, define the following fields:

    1.  Name

    2.  Description

    3.  Template Resource

> Note: When a resource is referenced in a **Calendar template**, a copy of the
resource’s calendar is associated with the **Calendar template**. If the working
hours of the template change, those changes will not propagate to the **Calendar
template**.

  
### See Also  
 [Set up resources](../psa/set-up-resources.md)
