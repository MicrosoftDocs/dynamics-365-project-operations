---
title: Booking statuses
description: This article provides a link to information about how to set up booking statuses for Project Operations.
author: ruhercul
ms.date: 11/05/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Booking statuses

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Whether your organization is operating in Centralized or Decentralized mode, there are 4 booking statuses available in Project Operations: Hard, Soft, Proposed and Canceled. Booking statuses are defined or updated during the booking process, are most commonly  established in three different ways:

-	Book from the team member grid
-	Book from the schedule board or schedule assistant
-	Book from the Project form

Details about each of these options is described in [Booking to a Project session](/dynamics365/project-operations/resource-management/book-project).

You can use the functionality provided in Universal Resource Scheduling for Dynamics 365 Field Service to set up booking statuses for your organization. For information on how to complete this set up, see [Set up booking statuses](/dynamics365/field-service/set-up-booking-statuses).

## Hard Booking

This booking status is used when the Resource Manager or the Project Manager wants to firmly allocate and reserve a resource to a Project. The resource is automatically added to the Project’s Team Member list and the resource’s capacity is consumed by the amount of time allocated to the project.

## Soft Booking

There are times when it is necessary to reserve a resource for a specific project but still allows it to be visible as allocatable to other projects while a decision about that specific booking allocation is taken. When Soft Booking, the resource’s capacity is not consumed and it is still seen as available to be allocated to other projects but the resource is added to the Project Team. 

## Proposed Booking

When operating in Centralized mode, Project Managers request resources with specific characteristics to Resource Manager and the Resource Manager, in turn, propose resources to that request using Proposed Booking. While a decision about that proposal is not taken, the resource’s capacity is not consumed, and the proposed resource is not added to the Project Team.

## Canceling a Booking

At any point in time, all Booking statuses can be Canceled. Canceling a booking frees Resource’s capacity allocated time but doesn’t remove the resource from the Project’s Team Member grid. 

## Resource Requirement Types

Due to Project Operations technical design, Bookings must always be performed against a resource requirement. The process to generate a resource requirement is available in the project’s Team Member Grid and can be for a Generic Resource or for a Named Resource.
When there is the need to book a resource directly to a project but there isn’t any specific request to that need (for example, when a Resource Manager or a Project Manager wants to allocate a resource to a project prior to have an Resource requirement)  it is possible to book the resource against the project requirement (known as Primary requirement, which is automatically created when a project is created).

## Change Booking Statuses

As projects naturally evolves, so do the Bookings – and the Bookings statuses must reflect these changes.  There are three ways Booking statuses can be updated:

-	in the Schedule Board, right-clicking in a specific Booking 
-	in the Maintain Bookings option, available when a Resource is highlighted in the Team Member grid
-	in the Resource Request cycle process – see [Booking to a Project session](/dynamics365/project-operations/resource-management/book-project) in Centralized resource booking

The following table describes the possible booking statuses changes and some typical situations when these changes are applicable:

| **Current Status** | **To Status** | **Typical Scenario** | **Impact on Capacity and Project Team Member** |
| --- | --- | --- | --- |
| Proposed | Soft | Resource Manager proposed a resource based on a Request, but the Project Manager is still not ready to confirm that booking | Adds resource to the Project Team Member |
| Proposed | Hard | Resource Manager proposed a resource based on a Request and the Project Manager wants to confirm that booking | Adds resource to the Project Team Member and Consumes Resource capacity|
| Proposed | Canceled | Resource Manager proposed a resource to a request and the Project Manager did not accept it | No impact |
| Soft | Hard | A Project that was waiting to be signed is confirmed and Proposed resources must be hard booked to the project | Consumes Resource capacity |
| Soft | Canceled | A Project that was waiting to be signed is cancelled and Proposed resources must be freed | No impact |
| Hard | Canceled | A task was suspended and a hard booked resource must be freed. |  Frees Resource Capacity |


## Recommennded Content

- [Resource bookings and how they relate to task assignments](dynamics365/project-operations/psa/faq-bookings-and-assignments?source=recommendations)
  This article provides information about how to manage named resources, resource bookings and task assignments and how they relate to each other.
  
- [Resource management modes overview](/dynamics365/project-operations/resource-management/resource-management-mode-overview?source=recommendations)
  This article provides information about Resource management functionality in Dynamics 365 Project Operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
