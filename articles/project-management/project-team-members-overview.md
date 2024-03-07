---
title: Project team members
description: This article provides information about how to work with project team member information, attributes, and scheduling.
author: ruhercul
ms.date: 10/01/2020
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: ruhercul

---

# Project team members

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project team members are the project participants who complete the work on a project. The objective of the team member grid is to provide a list of named resources who are committed to the engagement, and generic team members who are place holder resources and will be staffed later.

From the team member grid, the Project manager and the other project participants have the ability to see who has been committed to the project. They can also view a summary of their bookings, planned effort, and individual resource assignments. The team member grid allows Project managers to define resource requirements for generic team members and manage the bookings of existing team members.

The following table lists the key attributes of a project team member.

| Field name          | Description                                                                                                                                                                  |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Allocation method        | The allocation method used to book resources on the project.                                                                         |
| Billing Type             | Select whether the team member is classified as billable.                                                                                                                                       |
| Bookable Resource        | The bookable resource selected to replace the generic resource.                                                                                                                   |
| Delete Status            | The delete status of the team member to track if there is a delete request sent to PSS and whether PSS sends back response successfully and within the expected time window. |
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

- **Book**: For organizations that execute leveraging the hybrid bookings methodology, the book action will allow users to book a named resource based on the require requirements generated from the generic team member
- **Generate Requirement**: This action generates the requirement.
- **Specify Pattern**: Allows project managers to adjust resource requirement contours at a granular level. Project managers can adjust for the specific needs of the project in instances where the default distribution does not fit.
- **Submit Request**: For organizations using the central bookings methodology.
- **Edit**: Team member attributes can be edited including organizational unit, role, and position name.
- **Maintain Bookings**: When resources bookings need to be updated, maintain bookings allow the Project manager to adjust the:

    - Start
    - End
    - Total effort allocation

- **New**: In addition to adding resources directly from the schedule, Project managers can add new named or generic team members from the team member grid.
- **Delete**: By selecting one or many team members, the Project manager can delete resources who are no longer going to be participating on the project. Deleting a team member will also delete all associated resource assignments and  cancel all existing bookings.


[!INCLUDE[footer-include](../includes/footer-banner.md)]