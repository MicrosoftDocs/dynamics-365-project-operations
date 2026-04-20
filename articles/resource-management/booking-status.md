---
title: Booking statuses
description: This article provides information about how to set up booking statuses for Project Operations.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Booking statuses

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Regardless of whether your organization operates in **Centralized** mode or **Hybrid** mode (decentralized), Microsoft Dynamics 365 Project Operations provides four booking statuses: **Hard**, **Soft**, **Proposed**, and **Canceled**.

Define or update booking statuses during the booking process. You most often establish these statuses in three ways:

- Book from the **Team member** grid.
- Book from the **Schedule board** or **Schedule assistant**.
- Book from the **Project** page.

For more information about each of these options, see [Book to a Project](/dynamics365/project-operations/resource-management/book-project).

Use the functionality in Universal Resource Scheduling for Dynamics 365 Field Service to set up booking statuses for your organization. For information about how to complete this setup, see [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses).

## Hard booking

Use the **Hard** booking status when a resource manager or project manager wants to firmly allocate and reserve a resource to a project. The resource is automatically added to the project team, and the resource's capacity is consumed by the amount of time that's allocated to the project.

## Soft booking

Use the **Soft** booking status when you must reserve a resource for a specific project, but you want that resource to remain allocable to other projects until you make a final decision about the booking allocation. When you use soft booking, the resource's capacity isn't consumed and is available to other projects, but the resource is added to the project team.

## Proposed booking

When your organization operates in **Centralized** mode, project managers request resources that have specific characteristics, and the resource manager proposes resources for those requests by using proposed booking. Until a final decision about a proposal is made, the resource's capacity isn't consumed, and the proposed resource isn't added to the project team.

## Canceled booking

You can cancel all booking statuses at any point. When you cancel a booking, you free capacity-allocated time for resources, but you don't remove those resources from the project's **Team member** grid.

## Resource requirement types

Because of the technical design of Project Operations, you must always make bookings against a resource requirement. You can initiate the process for generating a resource requirement from the project's **Team member** grid. This process is available for both generic resources and named resources.

If you must book a resource directly to a project, but there's no specific request for that need, you can book the resource against the project requirement. This type of requirement is known as a primary requirement. The primary requirement is automatically created when the project is created. Use it when a resource manager or project manager wants to allocate a resource to a project before they have a resource requirement.

## Change booking statuses

As projects evolve, so do the bookings. The booking statuses must reflect any changes. You can update booking statuses in three places:

- In the **Schedule board**, by selecting and holding (or right-clicking) a specific booking.
- In the **Team member** grid, by using the **Maintain bookings** option that's available when a resource is selected.
- In the **Resource request cycle** process. For more information, see [Book to a project](/dynamics365/project-operations/resource-management/book-project) in **Centralized resource booking**.

The following table describes the booking status changes and some typical situations where the changes are applicable.

| Current status | New status | Typical scenario | Impact on capacity and the project team |
|---|---|---|---|
| Proposed | Soft | The resource manager proposes a resource based on a request, but the project manager isn't ready to confirm that booking. | The resource is added to the project's **Team member** grid. |
| Proposed | Hard | The resource manager proposes a resource based on a request, and the project manager wants to confirm that booking. | The resource is added to the project's **Team member** grid, and resource capacity is consumed. |
| Proposed | Canceled | The resource manager proposes a resource in a request, but the project manager doesn't accept the proposal. | No impact. |
| Soft | Hard | A project that was waiting to be started is confirmed, and the proposed resources must be hard booked to the project. | Resource capacity is consumed. |
| Soft | Canceled | A resource that was soft booked is no longer required in the project, and the booking must be removed. | No impact. |
| Hard | Canceled | A task was suspended, and a hard-booked resource must be freed. | Resource capacity is freed. |

## Recommended content

- [Resource bookings and how they relate to task assignments](../psa/faq-bookings-and-assignments.md) – This article provides information about how to manage named resources, resource bookings, and task assignments, and how these concepts relate to each other.
- [Resource management modes overview](resource-management-mode-overview.md) – This article provides information about Resource management functionality in Project Operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
