---
# required metadata

title: Resource reconciliation overview
description: This topic provides information about ensuring that resource bookings and assignments to projects are aligned.
author: ruhercul
manager: AnnBe
ms.date: 01/08/2021
ms.topic: article
ms.prod: 
ms.service: project-operations
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: ruhercul
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Resource reconciliation overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

For team members, bookings and assignments are loosely coupled. In other words, resources can have assignments but no bookings, or they can have bookings but no assignments. Ideally, bookings and assignments should be aligned, so that resources have committed capacity to perform the task assignments. However, the bookings might be based on availability, and task timings might change as the project continues. Therefore, the loose coupling of bookings and assignments provides flexibility.

The **Reconciliation** tab on the **Project** form lets project managers reconcile team members' bookings and their assignments for project teams.

The **Reconciliation** tab also shows bookings and assignments down to the level of the individual task assignment for each team member. Hours are displayed in cells that represent time periods from months down to days.

The tab also shows an overall net total for the project, together with a **Total** column.

For each resource, the tab calculates the difference between the team member's bookings and a rollup of the team member's task assignments. Ideally, this difference should be 0 (zero). In other words, there should be no difference between bookings and assignments. Differences are colored and shaded to draw attention to two conditions:

- **Booking shortage** – A booking shortage occurs when a resource has more assignments than bookings. Because this capacity hasn't been reserved, a project manager might want to correct this condition by extending the resource's bookings to cover the deficit.
- **Excess bookings** – Excess bookings occur when a resource has been booked to the project but hasn't been assigned to tasks. This condition might be acceptable in the cases where the resource was booked to the project before task assignment occurred. However, in other cases, the resource isn't planned to be assigned to tasks. In these cases, the project manager should consider canceling the resource's bookings, so that the capacity can be used for another project.

In some cases, when you view time at a higher level than the day level (for example, the month level), you might see a net difference of zero for a resource (in other words, bookings = assignments). However, if you view time at the week level, you might see that there are assignments of zero hours and bookings of 40 hours in the first week, but assignments of 40 hours and bookings of zero hours in the second week. Overall, the bookings and assignments are reconciled, but they differ from one week to the next.

When you view time at higher levels, cells in the **Reconciliation** tab have an indicator to inform you that there are differences at lower levels. By double-clicking in a cell, you can zoom in to view the difference. You can then right-click to zoom out. By selecting a resource and then using the **Next difference** control on the grid toolbar, you can go to the next difference between bookings and assignments for that resource. You can then use the **Previous difference** control to go back. You can also turn off the difference indicator and navigation behavior under **Settings**.


If you have task assignments for a resource but no bookings, on the **Projects** page, on the **Reconciliation** tab, select the booking shortage, and then select **Extend Booking**. The **Extend Booking** dialog box appears and shows the booking that is needed to address the resource's shortage. It also shows the resource's existing bookings across all projects or other schedulable entities. If you select **OK** to create the booking for the resource, regardless of that resource's availability, you might cause overbooking. Bookings that are generated with the **Extend Bookings** action are associated with the primary project requirement. When an extension is initiated, the specific requirement to be extendded can't be determined because as a resource, it could be associated with more than one requirement for the project.

The project manager or resource manager can then use the Schedule Board to manage any situations where a resource is overbooked beyond its capacity.

