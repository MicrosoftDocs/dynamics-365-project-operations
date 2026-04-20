---
title: Create bookable resources
description: Learn how to create bookable resources in Microsoft Dynamics 365 Project Operations. Follow step-by-step instructions to manage resources effectively.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Create bookable resources

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Resources are the most important asset of a project-based or service-based organization. You can create bookable resource in Microsoft Dynamics 365 Project Operations by using the **Resources** page.

## Create a bookable resource

1. In Project Operations, go to the **Resources** area, and then go to **Resource** \> **Resources**.
1. Select **New** to create a resource.
1. On the **General** tab, select a resource type. The resource type is a classification that describes who or what the resource is, and how it's related to your organization. Depending on the value that you select, you must define other related details. The following values are available:

    - **User** – The resource is a person or user in your company directory who can be scheduled or who requires access to the system.
    - **Account** or **Contact** – The resource isn't directly part of your organization, but you want to schedule it. For example, the resource might be a vendor company that doesn't have access to your system but provides services on your behalf.
    - **Equipment** – The resource is a piece of equipment that you want to schedule. For example, the resource might be a computer or a cell phone.

    > [!NOTE]
    > *Bookable resource* is a shared concept for applications that use Dataverse, such as Dynamics 365 Project Operations and Dynamics 365 Field Service. Project Operations doesn't support some of the bookable resource types, such as **Crew**, **Facility**, and **Pool**.

1. Enter the name of the resource, and define the details for it.
1. On the **Project Service** tab, define the target utilization for the resource (if applicable).
1. On the **Scheduling** tab, select the organizational unit that the resource belongs to, and enter other details (if applicable).
1. To make the resource available for scheduling on the schedule board, set the **Display On Schedule Board** option to **Yes**. For more information about how to show resources on the schedule board, see [Experience the schedule board in Universal Resource Scheduling](/dynamics365/common-scheduler/use-schedule-board).
1. Set the **Enable for Availability Search** option to define whether the [schedule assistant can return the resource](/dynamics365/common-scheduler/schedule-assistant) if it matches the criteria.
1. Save the record to view other details.

## Add work hours

For each resource, you can define work hours. Initially, the resource uses the default work hours. The schedule board uses colors to differentiate work hours and non-work hours. The schedule assistant returns only resources that have capacity in their designated work hours.

1. Open a resource record.
1. On the **Work hours** tab, you can either update existing hours for all events or select **New** \> **Working hours** to add more working or nonworking hours.
1. Set the start and end times of the resource's work hours, and select a repeat pattern. Use the *Custom* repeat pattern for recurring working hours, where resources can have different working hours on different days of the week.
1. To define the number of times that the resource can be booked during their work hours, enable the **Capacity** option. For example, you set the capacity to **5**. In this case, when you use the schedule assistant to book a resource, the resource appears as available and can be overbooked up to the capacity limit (in this case, five times). By default, the capacity is set to **1**. If you set the capacity to **0** (zero), the resource doesn't appear as available in a resource search.
1. Use the **Add break** option to split each working hours entry and add a break of 30 minutes. Use the **Add split** option to split each working hours entry evenly into two entries. Each of the resulting working hours entries can have a different capacity. The **Add split** option is available only if you enable the **Capacity** option.
1. Set the time zone for the resource work hours to ensure that the system uses them correctly.
1. Save the work hours to update the work hour calendar.

For more information about how to use code to edit work hour calendars, see [Edit work hour calendars by using APIs](/dynamics365/field-service/field-service-work-hours-calendar-api).

## Add resource roles

Resource categories are roles or groups of categories that help distinguish resources. Examples include a resource's role or job title.

A resource can have multiple categories. [Create resource roles](define-roles.md), and map them to a resource. If a resource has multiple roles assigned to it, one of them can be defined as the default role.

1. Go to the **Resources** area, and then go to **Resource** \> **Resources**.
1. Open a resource record, and select **Related** \> **Resource Category Assns**.
1. Select **New Resource Category Assns**.
1. Select a resource category in the lookup.

## Add skills and other characteristics

Characteristics represent a resource's skills and certifications. For example, a characteristic might be a specific skill, such as a CPR certification. Alternatively, it might be something more general, such as accounting or web development experience. It might even be something as simple as security clearance for a specific building. A certificate can be anything that the organization tracks for resources, such as a Project Management Professional (PMP) certificate for a Project Manager or a Six Sigma course completion certificate. For more information, see [Define skills and proficiencies](define-skills-proficiencies.md).

A resource can have multiple characteristics. [Create characteristics](/dynamics365/field-service/set-up-characteristics), map them to a resource, and provide a proficiency rating.

1. Go to the **Resources** area, and then go to **Resource** \> **Resources**.
1. Open a resource record, and select **Related** \> **Resource Characteristics**.
1. Select **Add New Bookable Resource Characteristics**.
1. Select a characteristic in the lookup.
1. Optional: Select a rating value for skill proficiency. Depending on the [proficiency model of the characteristic](/dynamics365/field-service/set-up-characteristics#create-a-proficiency-model), the value might represent a rating from 1 through 10 or the score on a certification exam.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
