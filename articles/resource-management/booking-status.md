---
title: Booking statuses
description: This article provides information about how to set up booking statuses for Project Operations.
author: tulsij
ms.author: tulsijhaveri
ms.date: 05/28/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Booking statuses

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Regardless of whether your organization is operating in **Centralized** mode or **Hybrid** mode (decentralized), four booking statuses are available in Microsoft Dynamics 365 Project Operations: **Hard**, **Soft**, **Proposed**, and **Canceled**.

Booking statuses are defined or updated during the booking process, and are most often established in three ways:

-	Book from the **Team member** grid.
-	Book from the **Schedule board** or **Schedule assistant**.
-	Book from the **Project** page.

For more information about each of these options, see [Book to a Project](/dynamics365/project-operations/resource-management/book-project).

You can use the functionality in Universal Resource Scheduling for Dynamics 365 Field Service to set up booking statuses for your organization. For information about how to complete this setup, see [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses).

## Hard booking

Use the **Hard** booking status when a resource manager or project manager wants to firmly allocate and reserve a resource to a project. The resource is automatically added to the project team, and the resource's capacity is consumed by the amount of time that's allocated to the project.

## Soft booking

Use the **Soft** booking status when you must reserve a resource for a specific project, but you want that resource to remain allocable to other projects until you make a final decision about the booking allocation. When you use soft booking, the resource's capacity isn't consumed and is available to other projects, but the resource is added to the project team.

## Proposed booking

When your organization is operating in **Centralized** mode, project managers request resources that have specific characteristics, and the resource manager proposes resources for those requests by using proposed booking. Until a final decision about a proposal is made, the resource's capacity isn't consumed, and the proposed resource isn't added to the project team.

## Canceled booking

All booking statuses can be canceled at any point. Cancellation of a booking frees capacity-allocated time for resources, but it doesn't remove those resources from the project's **Team member** grid.

## Resource requirement types

Because of the technical design of Project Operations, bookings must always be made against a resource requirement. The process for generating a resource requirement can be initiated from the project's **Team member** grid, and is available for both generic resources and named resources.

If you must book a resource directly to a project, but there's no specific request for that need, you can book the resource against the project requirement. This type of requirement is known as a primary requirement. It's automatically created when the project is created. You can use it when a resource manager or project manager wants to allocate a resource to a project before they have a resource requirement.

## Change booking statuses

As projects evolve, so do the bookings. The booking statuses must reflect any changes. Booking statuses can be updated in three places:

-	In the **Schedule board**, by selecting and holding (or right-clicking) a specific booking.
- In the **Team member** grid, by	using the **Maintain bookings** option that's available when a resource is selected.
-	In the **Resource request cycle** process. For more information, see [Book to a project](/dynamics365/project-operations/resource-management/book-project) in **Centralized resource booking**.

The following table describes the booking status changes and some typical situations where the changes are applicable.

| Current status | New status | Typical scenario | Impact on capacity and the project team |
|---|---|---|---|
| Proposed | Soft | The resource manager proposed a resource based on a request, but the project manager isn't ready to confirm that booking. | The resource is added to the project's **Team member** grid. |
| Proposed | Hard | The resource manager proposed a resource based on a request, and the project manager wants to confirm that booking. | The resource is added to the project's **Team member** grid, and resource capacity is consumed. |
| Proposed | Canceled | The resource manager proposed a resource in a request, but the project manager didn't accept the proposal. | No impact. |
| Soft | Hard | A project that was waiting to be started is confirmed, and the proposed resources must be hard booked to the project. | Resource capacity is consumed. |
| Soft | Canceled | A resource that was soft booked is no longer required in the project, and the booking must be removed. | No impact. |
| Hard | Canceled | A task was suspended, and a hard-booked resource must be freed. | Resource capacity is freed. |

## Recommended content

- [Resource bookings and how they relate to task assignments](../psa/faq-bookings-and-assignments.md) – This article provides information about how to manage named resources, resource bookings, and task assignments, and how these concepts relate to each other.
- [Resource management modes overview](resource-management-mode-overview.md) – This article provides information about Resource management functionality in Project Operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
