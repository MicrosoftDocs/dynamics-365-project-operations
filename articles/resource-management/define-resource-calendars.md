---
title: Define resource calendars
description: This article provides information about how to define the working hour calendars for resources in Project Operations.
author: tulsij
ms.author: dishantpopli
ms.date: 05/28/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Define resource calendars

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Each bookable resource working on a project must have a calendar of working hours to define their availability. Workings hours for a resource can be defined in two ways: 

   - Define individual calendar rules for a resource
   - Apply an existing calendar template for the resource

## Define a resource's working hours

1. On the **Resources** menu, select **Resources**.
2. From the grid view, select the applicable **Bookable Resource**.
3. On the **Resource Details** page, select the **Working Hours** tab. By default, the bookable resources calendar defaults to the working hours of the default work hour template that is defined for the organization.
4. To update the working hours, right-click on the start date of the proposed calendar rule to be defined. Use the calendar rule menu to define a calendar rule for a specific day, the remainder of the series, or the entire calendar.
5. After the option is selected, you can then define:

    - The day of the week where the working hours apply.
    - The working times within each day.
    - The time zone for the calendar rule.
    - If applicable, nonworking time can also be specified for the rule.
 
> [!NOTE]
> The capacity for the bookable resource must be equal to 1. Capacity greater than 1 is not supported by Project for the web.

## Applying a calendar template to a resource

1. On the **Resources** menu, select **Resources**.
2. From the grid view, select up to 25 **Bookable Resources** to update.
3. Select **Set Calendar** and a dialog prompts you with a list of available work hour templates.
4. Select the template you want to use, and then select **Apply**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
