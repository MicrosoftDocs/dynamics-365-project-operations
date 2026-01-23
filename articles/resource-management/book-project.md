---
title: Book to a project
description: This article provides information about booking a resource to a project.
author: tulsij
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: dishantpopli
---

# Book to a project

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

There are times where a Project Manager or Resource Manager needs to allocate a resource to project without a specific requirement being defined from a generic team member. This allocation can be achieved in one of three ways.

- Book from the team member grid
- Book from the schedule board
- Book from the **Project** form

## Book from the team member grid

If your organization is operating in hybrid Resource allocation mode, the Project manager can book a resource directly to the project by completing the following steps.

1. From the project, go to the team member grid and select **New**.
1. Define the position name and the role of the resource.
1. Select the bookable resource from the available lookup.
1. After you select the resource, define the following field information to book the resource:

    - Start date
    - Finish date
    - Allocation method
    - Hours, if applicable
    - Project approver

1. Select **Save and Close**

## Book from the schedule board

When a Resource Manager needs to book a resource directly to a project, they can use the schedule board and the project requirement. The project requirement is a resource requirement that is always available to be booked against. To book directly to a project from the schedule board, complete the following steps.

1. Go to the schedule board and on the left page
1. Filter for the resources you're considering for the requirement.
1. In the bottom pane, select the **Project** tab to view a list of project requirements.
1. Drag the requirement onto a resource and define the following information:

    - Start date
    - Finish date
    - Booking status
    - Booking method
    - Duration
   

## Book from the Project form

As a Project Manager, you might need to book a resource to a project, but only know the criteria rather than the name of the resource. Complete the following steps to use the schedule assistant to find a resource based on any available attributes of the resource. 

1. Navigate to the project and select **Book** to open the Schedule Assistant.
1. Using the filters on the left side of the Schedule Assistant, narrow the criteria and select **Search.**
1. Based on resources returned in the results, you can book a resource.

> [!NOTE]
> This method doesn't create any bookings for the resource. Instead, it adds the resource to the team. After the team member has been added to the
project, the Project Manager can use maintain bookings or extend bookings to add the required bookings to the resource.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
