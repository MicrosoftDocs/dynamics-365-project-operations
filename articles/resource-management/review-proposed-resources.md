---
# required metadata

title: Review proposed resources
description: This topic provides information about how to propose project resources.
author: ruhercul
manager: AnnBe
ms.date: 11/05/2020
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

# Review proposed resources

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Resource managers can propose a resource to the project manager by using a resource request.

1. From the request grid or the request itself, select **Find Resources**.
2. On the **Schedule Assistant** page, select the resource, and then, in the **Create Resource Booking** pane, in the **Booking Status** field, select **Book**.

The following status updates occur:

- On the **Schedule Assistant** page, the status indicators are updated to indicate that the booking is proposed, not hard-booked.
- On the resource request, the status is changed to **Needs Review**.
- On the **Team** tab of the project, the generic team member's **Request Status** value is changed to **Needs Review**.

The project manager can either accept or reject the proposal.

When resource managers process resource requests, they can use any of the following approaches:

- Propose multiple resources to satisfy the demand if no single resource is available to fulfill the required hours. Proposed hours are then split among multiple resources that can satisfy the required hours. In this scenario, the hours can't overlap.
- Propose fewer resources than are required. In this scenario, the proposed resource capacity is less than the required hours that the requestor specified. Therefore, when the requestor accepts the proposed resources, an unfulfilled resource requirement is created to capture the remaining demand.
- Book multiple resources to satisfy the demand if no single resource is available to complete the work.
- Book fewer resources than are required. In this scenario, the booked hours are fewer than the required hours. The system guides you to propose resources instead of bookings, so that the requestor can verify and keep track of remaining demand.

## Resource availability

It's critical that resource managers be able to view the availability of resources and update bookings. In some cases, there is no formal demand (resource request), but a resource manager must respond to an unplanned demand that comes through channels such as an email, phone call, or instant message. Resource managers use the Schedule Board to update resources and bookings.

Resource work hours are used as the basis for calculating the availability of a resource. Resource bookings consume the capacity of the resources.

The Schedule Board uses colors and shading to show bookings, availability, and overbookings, and also the status of bookings. A setting in the Schedule Board settings lets you show a legend.

If a right-pointing arrow appears next to an individual bookable resource on the Schedule Board, the resource can be expanded to show details of the work that the resource is booked on.

Because Dynamics 365 Project Operations uses the Universal Resource Scheduling engine, if you also have Dynamics 365 Field Service installed, you can view the details of resource bookings for projects, work orders, and any other entities that you've extended scheduling to.

To view more details about an individual resource, right-click it to open the resource card.

