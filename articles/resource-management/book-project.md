---
title: Book to a project
description: This topic provides information about booking a resource to a project.
author: ruhercul
ms.date: 01/24/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Book to a project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

There are times where a Project manager or Resource manager will need to allocate a resource to project without a specific requirement being defined from a generic team member. This can be achieved in one of three ways.

- Book from the team member grid
- Book from the schedule board
- Book from the **Project** form

## Book from the team member grid

If your organization is operating in hybrid Resource allocation mode, the Project manager can book a resource directly to the project by completing the following steps.

1. From the project, go to the team member grid and select **New**.
2. Define the position name and the role of the resource.
3. Select the bookable resource from the available lookup.
4. After you select the resource, define the following field information to book the resource:

    - Start date
    - Finish date
    - Allocation method
    - Hours, if applicable
    - Project approver

6. Select **Save and Close**

## Book from the schedule board

When a Resource manager needs to book a resource directly to a project, they can use the schedule board and the project requirement. The project requirement is a resource requirement that is always available to be booked against. To book directly to a project form the schedule board, complete the following steps.

1. Navigate to the schedule board and on the left page, filter for the resources you are considering for the requirement.
2. In the bottom pane, select the **Project** tab to view a list of project requirements.
3. Drag the requirement onto a resource and define the following information:

    - Start date
    - Finish date
    - Booking status
    - Booking method
    - Duration
   
   > [!NOTE]
   > Currently, Dynamics 365 Project Operations doesn't support the schedule board.   

## Book from the Project form

As a Project manager, you might need to book a resource to a project, but only know the criteria rather than the name of the resource. Complete the following steps to use the schedule assistant to find a resource based on any available attributes of the resource. 

1. Navigate to the project and select **Book** to open the Schedule Assistant.
2. Using the filters on the left side of the Schedule Assistant, narrow the criteria and select **Search.**
3. Based on resources returned in the results, you can book a resource.

> [!NOTE]
> This method doesn't create any bookings for the resource. Instead, it adds the resource to the team. After the team member has been added to the
project, the project manager can use maintain bookings or extend bookings to add the required bookings to the resource.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
