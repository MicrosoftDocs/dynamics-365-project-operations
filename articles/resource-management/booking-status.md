---
title: Booking statuses
description: This article provides information about how to set up booking statuses for Project Operations.
author: ruhercul
ms.date: 11/05/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Booking statuses

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Whether your organization is operating in **Centralized** or **Hybrid** mode (decentralized), there are four booking statuses available in Microsoft Dynamics 365 Project Operations: **Hard**, **Soft**, **Proposed**, and **Canceled**. Booking statuses are defined or updated during the booking process, and are most commonly established in three different ways:

-	Book from the **Team member** grid.
-	Book from the **Schedule board** or **Schedule assistant**.
-	Book from the **Project form**.

For more information about each of these options, see [Book to a Project](/dynamics365/project-operations/resource-management/book-project).

You can use the functionality provided in **Universal Resource Scheduling** for Microsoft Dynamics 365 Field Service to set up booking statuses for your organization. For information on how to complete this set up, see [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses).

## Hard booking

Use the hard booking status when the Resource Manager or the Project Manager wants to firmly allocate and reserve a resource to a Project. The resource is automatically added to the Project’s team member list, and the resource’s capacity is consumed by the amount of time allocated to the project.

## Soft booking

Use the soft booking status when you need to reserve a resource for a specific project, but want keep their status as allocatable to other projects until you make a final decision about that specific booking allocation. When using soft booking, the resource’s capacity isn't consumed, and is available to other projects, but the resource is added to the project team. 

## Proposed booking

When operating in **Centralized** mode, Project Managers request resources with specific characteristics, and the Resource Manager proposes resources for that request using **Proposed booking**. Until a final decision about that proposal is made, the resource’s capacity isn't consumed, and the proposed resource isn't added to the project team.

## Canceling a booking

At any point in time, all booking statuses can be canceled. Canceling a booking frees capacity allocated time for resources, but doesn’t remove them from the project’s **Team member** grid. 

## Resource requirement types

Due to Project Operations technical design, bookings must always be performed against a resource requirement. The process to generate a resource requirement is available in the project’s **Team member** grid and can be for a **Generic resource** or for a **Named resource**.

When you need to book a resource directly to a project, but there isn’t a specific request for that need, it's possible to book the resource against the project requirement. This is known as a primary requirement, and it is created automatically when the project is created. You can use this when a Resource Manager or a Project Manager wants to allocate a resource to a project prior to having a resource requirement. 

## Change booking statuses

As projects naturally evolve, so do the bookings, and the bookings statuses must reflect these changes. There are three ways booking statuses can be updated:

-	In the **Schedule board** by right-clicking in a specific Booking. 
-	In the **Maintain bookings** option, available when a resource is highlighted in the **Team member** grid.
-	In the **Resource request cycle** process. For more information, see [Booking to a Project session](/dynamics365/project-operations/resource-management/book-project) in **Centralized resource booking**.

The following table describes the booking status changes and some of the typical situations when these changes are applicable:

| **Current Status** | **To Status** | **Typical Scenario** | **Impact on Capacity and Project Team Member** |
| --- | --- | --- | --- |
| Proposed | Soft | The Resource Manager proposed a resource based on a request, but the Project Manager is not ready to confirm that booking. | Adds the resource to the project **Team member** grid. |
| Proposed | Hard | The Resource Manager proposed a resource based on a request, and the Project Manager wants to confirm that booking. | Adds the resource to the project **Team member** grid and consumes resource capacity. |
| Proposed | Canceled | The Resource Manager proposed a resource on a request, and the Project Manager didn't accept it. | No impact. |
| Soft | Hard | A project that was waiting to start is confirmed and the proposed resources must be hard booked to the project. | Consumes Resource capacity. |
| Soft | Canceled | A resource that was soft booked is no longer needed in the project, and the booking must be removed. | No impact. |
| Hard | Canceled | A task was suspended, and a hard booked resource must be freed. |  Frees Resource Capacity. |


## Recommended content

- [Resource bookings and how they relate to task assignments](../psa/faq-bookings-and-assignments.md)
  This article provides information about how to manage named resources, resource bookings and task assignments and how they relate to each other.
  
- [Resource management modes overview](resource-management-mode-overview.md)
  This article provides information about Resource management functionality in Dynamics 365 Project Operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
