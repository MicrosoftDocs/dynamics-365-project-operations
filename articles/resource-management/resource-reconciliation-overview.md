---
title: Resource reconciliation overview
description: This article provides information that will help you ensure that resource bookings and assignments for projects are aligned.
author: abriccetti
ms.author: abriccetti
ms.date: 08/15/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Resource reconciliation overview

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

For team members, bookings and assignments are loosely coupled. In other words, resources can have assignments and no bookings, or they can have bookings and no assignments. Ideally, bookings and assignments should be aligned, so that resources have committed capacity to perform the task assignments. However, the bookings might be based on availability, and task timings might change as the project continues. Therefore, the loose coupling of bookings and assignments provides flexibility.

There are two ways to reconcile the differences between bookings and assignments. This article explains how to use the **Resource Reconciliation** tab on project records. For information about how to use the bulk reconciliation API, see [Reconcile Projects with Bulk Reconciliation](bulk-reconciliation-dev.md).

The **Reconciliation** tab on the **Projects** page lets project managers reconcile team members' bookings and their assignments for project teams.

The **Reconciliation** tab shows bookings and assignments down to the level of the individual task assignment for each team member. Hours are shown in cells that represent periods from months to days. The tab also shows an overall net total for the project, together with a **Total** column.

For each resource, the **Reconciliation** tab calculates the difference between the team member's bookings and a rollup of that team member's task assignments. Ideally, this difference should be 0 (zero). In other words, there should be no difference between bookings and assignments. Differences are colored and shaded to draw attention to two conditions:

- **Booking shortage** – A booking shortage occurs when a resource has more assignments than bookings. Because the capacity hasn't been reserved, the project manager might want to correct this condition by extending the resource's bookings to cover the deficit.
- **Excess bookings** – Excess bookings occur when a resource has been booked to the project but hasn't been assigned to tasks. This condition might be acceptable in cases where the resource was booked to the project before task assignment occurred. However, in other cases, where there is no plan to assign the resource to tasks, the project manager should consider canceling the resource's bookings. In that way, the capacity can be used for another project.

In some cases, when you view time at a higher level than the day level (for example, the month level), you might see a net difference of zero for a resource (in other words, bookings equal assignments). However, if you view time at the week level, you might see that there are assignments of zero hours and bookings of 40 hours in the first week, but assignments of 40 hours and bookings of zero hours in the second week. Overall, the bookings and assignments are reconciled, but they differ from one week to the next.

When you view time at higher levels, cells on the **Reconciliation** tab have an indicator to inform you that there are differences at lower levels. By double-tapping or double-clicking in a cell, you can zoom in to view the difference. You can then select and hold (or right-click) to zoom out. By selecting a resource and then using the **Next difference** control on the grid toolbar, you can go to the next difference between bookings and assignments for that resource. You can then use the **Previous difference** control to go back. You can also turn off the difference indicator and navigation behavior under **Settings**.

If you have task assignments for a resource but no bookings, select the booking shortage on the **Reconciliation** tab of the **Projects** page, and then select **Extend Booking**. The **Extend Booking** dialog box that appears shows the booking that is required to address the resource's shortage. The dialog box also shows the resource's existing bookings across all projects or other schedulable entities. If you select **OK** to create the booking for the resource, regardless of that resource's availability, you might cause overbooking.

Bookings that are created through the **Extend Booking** action are associated with the primary project requirement. When an extension is initiated, the specific requirement that must be extended can't be determined, because the resource might be associated with more than one requirement for the project.

The project manager or resource manager can then use the Schedule board to manage any situations where a resource is overbooked beyond its capacity.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
