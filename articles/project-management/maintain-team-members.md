---
title: Maintain team members
description: Learn how to book named resources to project teams and assign them to tasks in Dynamics 365 Project Operations. Follow step-by-step instructions to maintain team members effectively.
author: abriccetti
ms.author: abriccetti
ms.date: 02/05/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Maintain team members

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Add a named resource to your project team by booking them directly to the team.

1. In Dynamics 365 Project Operations, go to **Projects**, and select the open project that you're booking for.
1. On the **Project** page, on the **Team** tab, select **New**.
1. In the **Quick Create Project Team Member** dialog box, select the bookable resource. The **Role** field populates with the resource's default role if they have one assigned. You can change the role.
1. Select the from and to dates that the resource is needed, and select the allocation method of the resource's capacity.
1. In the **Project Approver** field, select **Yes** if you want the team member to be a project approver. The team member can approve submitted time and expense entries for this project.
1. Select **Save**.

You can now assign the booked resource to tasks on the project. On the **Project** page, on the **Schedule** tab, assign tasks to the new resource. The resource picker that is launched from the **Resources** field in the task grid shows the team members that you can select.

In Project Operations, resource bookings and task assignments aren't tightly coupled. When you use the resource picker in the schedule, you can assign tasks to team members for more hours than their bookings cover on the project.

The differences between team member bookings and assignments are shown on the **Team** and **Resource Reconciliation** tabs. You can also reconcile the differences between bookings and assignments for resources at a more detailed level.

Use the resource picker on the **Schedule** tab to search for and select bookable resources that aren't already part of the project team. These resources are shown in the resource picker as **Other Resources**.

When you make a selection, you add the resource to the project team and assign it to the task, but you don't generate bookings.

You can use the **Reconciliation** tab’s extend booking capability or the **Schedule Board** to book the resource’s capacity to the project.

After you book a team member on your project, use **Maintain bookings** or the **Schedule Board** directly to manage their bookings.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
