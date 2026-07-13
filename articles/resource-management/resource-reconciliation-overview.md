---
title: Resource reconciliation overview
description: This article provides information that will help you ensure that resource bookings and assignments for projects are aligned.
author: abriccetti
ms.author: abriccetti
ms.date: 07/13/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Resource reconciliation overview

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

For team members, bookings and assignments are loosely coupled. In other words, resources can have assignments and no bookings, or they can have bookings and no assignments. Ideally, bookings and assignments align, so resources have committed capacity to perform the task assignments. However, the bookings might be based on availability, and task timings might change as the project continues. Therefore, the loose coupling of bookings and assignments provides flexibility.

You can reconcile the differences between bookings and assignments in two ways. This article explains how to use the **Resource Reconciliation** tab on project records. For information about how to use the bulk reconciliation API, see [Reconcile Projects with Bulk Reconciliation](bulk-reconciliation-dev.md).

## Resource Reconciliation UI for Projects

The **Reconciliation** tab on the **Projects** page lets project managers reconcile team members' bookings and their assignments for project teams.

The **Reconciliation** tab shows bookings and assignments down to the level of the individual task assignment for each team member. Hours are shown in cells that represent periods from months to days. The tab also shows an overall net total for the project, together with a **Total** column.

For each resource, the **Reconciliation** tab calculates the difference between the team member's bookings and a rollup of that team member's task assignments. Ideally, this difference is 0 (zero). In other words, there should be no difference between bookings and assignments. Differences are colored and shaded to draw attention to two conditions:

- **Booking shortage** – A booking shortage occurs when a resource has more assignments than bookings. Because the capacity isn't reserved, the project manager might want to correct this condition by extending the resource's bookings to cover the deficit.
- **Excess bookings** – Excess bookings occur when a resource is booked to the project but isn't assigned to tasks. This condition might be acceptable in cases where the resource was booked to the project before task assignment occurred. However, in other cases, where there's no plan to assign the resource to tasks, the project manager should consider canceling the resource's bookings. In that way, the capacity can be used for another project.

In some cases, when you view time at a higher level than the day level (for example, the month level), you might see a net difference of zero for a resource (in other words, bookings equal assignments). However, if you view time at the week level, you might see that there are assignments of zero hours and bookings of 40 hours in the first week, but assignments of 40 hours and bookings of zero hours in the second week. Overall, the bookings and assignments are reconciled, but they differ from one week to the next.

When you view time at higher levels, cells on the **Reconciliation** tab have an indicator to inform you that there are differences at lower levels. By double-tapping or double-clicking in a cell, you can zoom in to view the difference. You can then select and hold (or right-click) to zoom out. By selecting a resource and then using the **Next difference** control on the grid toolbar, you can go to the next difference between bookings and assignments for that resource. You can then use the **Previous difference** control to go back. You can also turn off the difference indicator and navigation behavior under **Settings**.

If you have task assignments for a resource but no bookings, select the booking shortage on the **Reconciliation** tab of the **Projects** page, and then select **Extend Booking**. The **Extend Booking** dialog box that appears shows the booking that is required to address the resource's shortage. The dialog box also shows the resource's existing bookings across all projects or other schedulable entities. If you select **OK** to create the booking for the resource, regardless of that resource's availability, you might cause overbooking.

Bookings that you create through the **Extend Booking** action are associated with the primary project requirement. When an extension is initiated, the specific requirement that must be extended can't be determined, because the resource might be associated with more than one requirement for the project.

## Bulk Resource Reconciliation UI (Preview)

The **Resource Reconciliation** grid for a project previously let you reconcile only booking shortages, one time slice (day, week, or month) at a time, by using the **Extend booking** action. The new Bulk Resource Reconciliation preview feature lets resource managers and project managers reconcile booking shortages or excesses, across multiple resources and time slices, in a single action.

> [!NOTE]
> The underlying action uses the same business logic as the Bulk Reconciliation API.

### Enable the Bulk Resource Reconciliation (preview) feature

To enable bulk reconciliation of resources on a project, follow these steps:

1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. Select **Enable bulk resource reconciliation**.

### Reconcile resources across multiple time slices

After you enable the feature, you can reconcile one or more time slices in either of the following ways:

- Select one or more time slices on the grid.
- Select **Reconcile Bookings** to reconcile only the selected slices. This action works across both booking shortages and excess bookings.
- A side pane appears summarizing the net booking excess, net booking shortage, and list of resources for which reconciliation is being initiated.
- Select **Reconcile** to start the process.
- A notification appears at the top of the screen indicating that bulk reconciliation is initiated. In-app notifications communicate completion of this process. Any failures in reconciliation are also communicated as part of the notification.
- Refresh the reconciliation grid after receiving a notification for action completion to see the updated bookings.

> [!NOTE]
> Reconciliation of bookings only affects time slices that show a difference between assigned hours and booked capacity on the grid. The process skips time slices that are already reconciled.

### Reconcile all resources for a project

- Instead of selecting time slices for multiple resources, select the **Reconcile All** action above the grid.
- A side pane appears to highlight all resources for which time slices are identified for reconciliation.
- You can deselect one or more resources from the list before continuing.
- Select **Reconcile** to start the process.

> [!NOTE]
> **Reconcile All** can initiate a large number of booking modifications and can take a significant amount of time to complete. Use this capability sparingly and on smaller projects only.

The project manager or resource manager can use the Schedule board to manage any situations where a resource is overbooked beyond its capacity.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
