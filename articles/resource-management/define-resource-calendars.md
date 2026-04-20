---
title: Define resource calendars
description: This article provides information about how to define the working hour calendars for resources in Project Operations.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Define resource calendars

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Each bookable resource working on a project needs a calendar of working hours to define their availability. You can define working hours for a resource in two ways:

- Define individual calendar rules for a resource.
- Apply an existing calendar template for the resource.

## Define a resource's working hours

1. On the **Resources** menu, select **Resources**.
1. From the grid view, select the applicable **Bookable Resource**.
1. On the **Resource Details** page, select the **Working Hours** tab. By default, the bookable resource's calendar uses the working hours of the default work hour template that is defined for the organization.
1. To update the working hours, right-click on the start date of the proposed calendar rule to be defined. Use the calendar rule menu to define a calendar rule for a specific day, the remainder of the series, or the entire calendar.
1. After you select the option, you can define:

    - The day of the week where the working hours apply.
    - The working times within each day.
    - The time zone for the calendar rule.
    - If applicable, nonworking time for the rule.

> [!NOTE]
> The capacity for the bookable resource must be equal to 1. Project for the web doesn't support capacity greater than 1.

## Apply a calendar template to a resource

1. On the **Resources** menu, select **Resources**.
1. From the grid view, select up to 25 **Bookable Resources** to update.
1. Select **Set Calendar**. A dialog box prompts you with a list of available work hour templates.
1. Select the template you want to use, and then select **Apply**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
