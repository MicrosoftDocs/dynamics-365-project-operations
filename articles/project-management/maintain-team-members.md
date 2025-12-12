---
title: Maintain team members
description: This article provides information about booking named resources to project teams and assigning them to tasks. 
author: abriccetti
ms.author: abriccetti
ms.date: 05/21/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Maintain team members

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You can add a named resource to your project team by booking them directly to the team.

1. In Dynamics 365 Project Operations, go to **Projects**, and select the open the project that you're booking for.
2. On the **Project** page, on the **Team** tab, select **New**. 
3. In the **Quick Create Project Team Member** dialog box, select the bookable resource. The **Role** field will populate with the resource's default role if they have one assigned. You can change the role. 
4. Select the from and to dates that the resource will be needed, and select the allocation method of the resource's capacity. 
5. In the **Project Approver** field, select **Yes** if you want the team member to be a project approver. The team member can approve submitted time and expense entries for this project. 
6. Select **Save**.

You can now assign the booked resource to tasks on the project. On the **Project** page, on the **Schedule** tab, assign tasks to the new resource. The resource picker that is launched from the **Resources** field in the task grid will show the team members that you can select.


In Project Operations, resource bookings and task assignments aren't tightly coupled. When you use the resource picker in the schedule, you can assign tasks to team members for more hours than their bookings cover on the project.

The differences between team member bookings and assignments are shown on the **Team** and **Resource Reconciliation** tabs. You can also reconcile the differences between bookings and assignments for resources at a more detailed level.

Use the resource picker on the **Schedule** tab to search for and select bookable resources that are not already part of the project team. These resources are shown in the resource picker as **Other Resources**.

When you make a selection, the resource is added to the project team and assigned to the task, but no bookings are generated.

You can use the **Reconciliation** tab’s extend booking capability or the **Schedule Board** to book the resource’s capacity to the project.

After a team member is booked on your project, you can use **Maintain bookings** or the **Schedule Board** directly to manage their bookings.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
