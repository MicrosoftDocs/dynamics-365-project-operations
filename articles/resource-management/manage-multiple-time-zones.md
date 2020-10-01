---
title: Managing time zones
description: When a project is created, its time zone is based upon the time zone defined in the work hour template applied.
author: 
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-project-operations
ms.reviewer: kfend 
ms.author: 

---

Managing time zones
===================

Projects
--------

When a project is created, its time zone is based upon the time zone defined in
the work hour template applied. When viewing the **Project summary** tab, the dates
will always be relative to the logged in user’s time zone. This is true for all
other tabs in the project form, except the **Task** tab. When viewing the work
breakdown structure, the dates will always be displayed in the project’s time
zone.

Tasks
-----

When a task is created, its start time, end time and hours/day will be governed
by the working hours of the project. For example, if a task is created with a
project whose time zone is -8 PST and has the following working hours: 9:00 AM to 5:00 PM
Monday to Friday, any task created without an assignment will respect the start
time and end time of the project calendar.

Managing resources with time zones
----------------------------------

To ensure accurate and predictable results when using Extend Booking, there are two key prerequisites that must be met:  

- The user must configure their device's time zone to match the time zone defined in your system's Personalization Settings.
 
  ![Time zone settings in Windows 10](media/reconcile-assignments-03.png)

  ![Time zone settings in personalization settings](media/reconcile-assignments-04.png)
 
- The Bookable Resource must have at least one minute of working time that overlaps with the contours that are used to define the requested extension. For instance, the following example shows review resources with working hours that fall between 9:00 AM and 7:00 PM. 

  ![Comparison of resource contours](media/reconcile-assignments-05.png)

The following table shows:

- A project calendar template.
- Resource A: This resource has the same calendar and is in the same time zone as the project. The start time of the bookings will be 9:00 AM.
- Resources B: This resource is located in a different time zone than the project and therefore starts at 7:00 AM in their time zone. However, the bookings will begin at 9:00 AM as that is the earliest start time of the assignment contour.
- Resources C and D: The resources are also located in different time zones, both different from each other and the project, and their bookings start no earlier than their respective available start times.

|Entity  |Calendar  |
|-|-|
|Project calendar template   | ![project calendar](media/reconcile-assignments-06.png) |
|Resource A  | ![Resource A calendar](media/reconcile-assignments-06.png) |
|Resource B  |  ![Resource B calendar](media/reconcile-assignments-07.png) |
|Resource C  |  ![Resource C calendar](media/reconcile-assignments-08.png) |
|Resource D  | ![Resource D calendar](media/reconcile-assignments-09.png)  |
 
When you navigate to the reconciliation view, the resource assignments and the associated booking shortages will be displayed.

![Reconciliation view before extension](media/reconcile-assignments-10.png)

After the Extend Booking functionality has been executed on each resource, bookings are successfully extended for each resource. This is because each resource’s working hours overlapped with the contours of the shortage.

![Reconciliation view after booking extension](media/reconcile-assignments-11.png) 

However, a closer look at the details of the bookings shows differences in the start time of the bookings. The bookings will start no earlier than the start time of the assignment contour and no earlier than the available start time of the resource.

![New bookings of the resources in the schedule board](media/reconcile-assignments-12.png)
