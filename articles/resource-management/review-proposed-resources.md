---
# required metadata

title: Review proposed resources
description: This article provides information about how to propose project resources.
author: ruhercul
ms.date: 07/19/2022
ms.topic: article
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
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

To review proposed resources, follow these steps:

1. From the **Request** grid, or the request itself, select **Find Resources**.
2. On the **Schedule Assistant** page, select the resource and then confirm that all proposed hours are included in the proposed booking.
3. In the **Create Resource Booking** pane, set the **Booking Status** field to **Proposed**, and then select **Book**.

    > [!NOTE]
    > Setting the **Booking Status** to **Proposed** doesn't hard book the resource and doesn't replace the generic resource with the named team member.

    The following status updates occur:

    - On the **Schedule Assistant** page, the status indicators are updated to indicate that the booking is proposed, not hard booked.
    - On the resource request, the reviewer of the request should change the status to **Needs Review**.
    - On the **Team** tab of the project, the generic team member's **Request Status** value is automatically changed to **Needs Review**.

The project manager can accept or reject the proposal.

When resource managers process resource requests, they can use any of the following approaches:

- Propose multiple resources to satisfy the demand if no single resource is available to fulfill the required hours. Proposed hours are then split among multiple resources that can satisfy the required hours. In this scenario, the hours can't overlap.
- Propose fewer resources than are required. In this scenario, the proposed resource capacity is less than the required hours that the requestor specified. When the requestor accepts the proposed resources, an unfulfilled resource requirement is created to capture the remaining demand.
- Book multiple resources to satisfy the demand if no single resource is available to complete the work.
- Book fewer resources than required. In this scenario, the booked hours are fewer than the required hours. The system guides you to propose resources instead of bookings so that the requestor can verify and keep track of remaining demand.

## Resource availability

Resource managers must be able to view the availability of resources and update bookings. In some cases, there is no formal demand (resource request). However, a resource manager must respond to an unplanned demand that comes through other channels such as emails, phone calls, or instant messages. Resource managers use the **Schedule Board** to update resources and bookings.

Resource work hours are used as the basis to calculate the availability of a resource. Resource bookings consume the capacity of the resources.

The **Schedule Board** uses colors and shading to show bookings, availability, overbookings, and the status of bookings. A setting on the **Schedule Board** lets you display a legend.

If a right-pointing arrow appears next to an individual bookable resource on the **Schedule Board**, the resource can be expanded to show details of the work that the resource is booked on.

Because Dynamics 365 Project Operations uses the Universal Resource Scheduling engine, if you also have Dynamics 365 Field Service installed, you can view the details of resource bookings for projects, work orders, and any other entities that you've extended scheduling to.

To view additional details about an individual resource, right-click it to open the resource card.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
