---
title: Project team members
description: This article provides information about how to work with project team member information, attributes, and scheduling.
author: abriccetti
ms.date: 03/12/2024
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: abriccetti

---

# Project team members

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Project team members are the project participants who complete the work on a project. The objective of the team member grid is to provide a list of named resources who are committed to the engagement, and generic team members who are place holder resources and are staffed later.

From the team member grid, the Project manager and the other project participants have the ability to see who has been committed to the project. They can also view a summary of their bookings, planned effort, and individual resource assignments. The team member grid allows Project managers to define resource requirements for generic team members and manage the bookings of existing team members.

The following table lists the key attributes of a project team member.

| Field name          | Description                                                                                                                                                                  |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Allocation method        | The allocation method used to book resources on the project.                                                                         |
| Billing Type             | Select whether the team member is classified as billable.                                                                                                                                       |
| Bookable Resource        | The bookable resource selected to replace the generic resource.                                                                                                                   |
| Delete Status            | The **Delete status** of the team member to track if there's a delete request sent to PSS and whether PSS sends back response successfully and within the expected time window. |
| Total Effort (Hours)     | The sum of the team member's effort on their assignments.                                                                                                                         |
| Effort Completed (Hours) | A tracking of the effort accomplished by the team member on their assignments.                                                                                           |
| Effort Remaining (Hours) | A tracking of the effort not yet completed by the team member on their assignments.                                                                                    |
| Finish                   | The resource team membership end date.                                                                                                                                            |
| Hard Booked Hours        | The hard booked hours of the team member.                                                                                                                                                                |
| Position Name            | The name used to identify the generic resource.                                                                                                                                   |
| Resourcing Unit          | The organizational unit of the resource performing the work.                                                                                                                      |
| Project Approver         | Select whether the team member can approve time and expenses.                                                                                                                     |
| Required Hours           | The required hours of the team member from team member requirement.                                                                                                                       |
| Role                     | The role the team member fills on this team.                                                                                                                                |
| Position Description     | Enter a description of the role for this team member.                                                                                                                             |
| Soft Booked Hours        | The soft booked hours of the team member.                                                                                                                                                                 |
| Start                    | The resource team membership start date.                                                                                                                                          |

From the team member grid, the following actions can be taken:

- **Book**: For organizations that execute using the hybrid bookings methodology, the book action allows users to book a named resource based on the requirements generated from the generic team member
- **Generate Requirement**: This action generates the requirement.
- **Specify Pattern**: Allows project managers to adjust resource requirement contours at a granular level. Project managers can adjust for the specific needs of the project in instances where the default distribution doesn't fit.
- **Submit Request**: For organizations using the central bookings methodology.
- **Edit**: Team member attributes can be edited including organizational unit, role, and position name.
- **Maintain Bookings**: When resources bookings need to be updated, maintain bookings allow the Project manager to adjust the:

    - Start
    - End
    - Total effort allocation

- **New**: In addition to adding resources directly from the schedule, Project managers can add new named or generic team members from the team member grid.
- **Delete**: If you select one or many team members, the Project manager can delete resources who are no longer going to be participating on the project. Deleting a team member also deletes all associated resource assignments and cancels all existing bookings. The delete operation is asynchronous and may take some time to complete. During this process the team member record can't be modified. The status of the delete action is tracked by the **Delete status** attribute. If the delete operation doesn't succeed within three minutes, the **Delete status** updates to **Error** and then you can retry the delete action.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
