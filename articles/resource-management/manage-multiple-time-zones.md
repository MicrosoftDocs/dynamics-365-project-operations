---
title: Manage time zones
description: When a project is created, its time zone is based upon the time zone defined in the work hour template applied.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage time zones

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

## Projects

When you create a project, you set the time zone based on the time zone defined in the work hour template you apply. On the **Project** form, the dates always relate to the time zone of the user who's signed in on each tab, except the **Task** tab. When you view the work breakdown structure, the dates always display in the project's time zone.

## Tasks

When you create a task, the working hours of the project control the start time, end time, and hours per day. For example, if you create a task with a project whose time zone is -8 PST and has the following working hours: 9:00 AM to 5:00 PM Monday to Friday, any task you create without an assignment respects the start time and end time of the project calendar.

## Manage resources with time zones

To get accurate and predictable results when using **Extend Booking**, make sure you meet these two key prerequisites:  

- Set your device's time zone to match the time zone defined in the system's **Personalization Settings**.
 
  :::image type="content" source="media/reconcile-assignments-03.png" alt-text="Screenshot of time zone settings in Windows 10.":::

  :::image type="content" source="media/reconcile-assignments-04.png" alt-text="Screenshot of time zone settings in personalization settings.":::
 
- The bookable resource must have at least one minute of working time that overlaps with the contours that define the requested extension. For example, the following resources have working hours that fall between 9:00 AM and 7:00 PM. 

  :::image type="content" source="media/reconcile-assignments-05.png" alt-text="Screenshot of comparison of resource contours.":::

The following table shows:

- A project calendar template
- Resource A: This resource has the same calendar and is in the same time zone as the project. The start time of the bookings is 9:00 AM.
- Resource B: This resource is in a different time zone than the project and starts at 7:00 AM in their time zone. However, the bookings start at 9:00 AM as that is the earliest start time of the assignment contour.
- Resources C and D: The resources are in different time zones, both different from each other and the project, and their bookings start no earlier than their respective available start times.

|Entity  |Calendar  |
|-|-|
|Project calendar template   | :::image type="content" source="media/reconcile-assignments-06.png" alt-text="Screenshot of project calendar template."::: |
|Resource A  | :::image type="content" source="media/reconcile-assignments-06.png" alt-text="Screenshot of Resource A calendar."::: |
|Resource B  |  :::image type="content" source="media/reconcile-assignments-07.png" alt-text="Screenshot of Resource B calendar."::: |
|Resource C  |  :::image type="content" source="media/reconcile-assignments-08.png" alt-text="Screenshot of Resource C calendar."::: |
|Resource D  | :::image type="content" source="media/reconcile-assignments-09.png" alt-text="Screenshot of Resource D calendar.":::  |
 
When you go to the **Reconciliation** view, you see the resource assignments and the associated booking shortages.

:::image type="content" source="media/reconcile-assignments-10.png" alt-text="Screenshot of the Reconciliation view before extension.":::

After you use the extend booking functionality for each resource, the bookings are successfully extended for each resource because each resource's working hours overlapped with the contours of the shortage.

:::image type="content" source="media/reconcile-assignments-11.png" alt-text="Screenshot of the Reconciliation view after booking extension.":::

A closer look at the details of the bookings shows differences in the start time of the bookings. The bookings start no earlier than the start time of the assignment contour and no earlier than the available start time of the resource.

:::image type="content" source="media/reconcile-assignments-12.png" alt-text="Screenshot of new bookings of the resources in the schedule board.":::


[!INCLUDE[footer-include](../includes/footer-banner.md)]
