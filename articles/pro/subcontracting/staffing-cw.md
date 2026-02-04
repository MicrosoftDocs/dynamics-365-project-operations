---
title: Staffing a project with contract workers and subcontracted capacity
description: This article explains how project requirements can be staffed using contract workers or subcontracted capacity in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Staffing a project with contract workers and subcontracted capacity

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You can staff generic project team members with employees or contract workers. When you staff a project with contract workers, you can limit your staffing options to specific contract workers that are assigned to a subcontract line.

## Search for staff resource requirements with contract workers that belong to a specific subcontract line

To search for and staff resource requirements by using contract workers that belong to a specific subcontract line, follow these steps:

1. Create a generic project team member that references a subcontract and subcontract line.
1. Generate a resource requirement for this generic project team member by using the **Generate requirement** button on the project team members sub grid.
1. Select the team member row and then select the **Book** button on the sub grid.
1. This action opens the Schedule Board with the requirement context. Along with other attributes such as dates, role, and organizational unit fields, the Schedule Board filters are also automatically populated with the vendor, subcontract, and subcontract line fields from the resource requirement.
1. The system searches for resources that meet the filter criteria and lists them.
1. Select one of the filtered resources and book the resource for the requirement.
1. A project team member is created and updated with subcontract and subcontract line references. Go to **Project Estimates** and select **Update prices** to see the updated cost of the resource assignment.

> [!NOTE]
> You might not always be able to update the project team member with a subcontract and subcontract line reference during the booking if the resource is assigned to multiple subcontract lines. If the system can't update the project team member with a subcontract and subcontract line, open the project team member record and manually update these fields so that the financial cost estimate accurately reflects the subcontractor cost.

## Search for and staff resource requirements with any contract worker

To search for and staff resource requirements with any contract worker, follow these steps:

1. Create a generic project team member.
1. Generate a resource requirement for this generic project team member by using the **Generate requirement** button on the project team members sub grid.
1. Select the team member row and then select the **Book** button on the sub grid.
1. This selection opens the Schedule Board with the requirement context. Along with other attributes such as dates, role, and organizational unit fields, the Schedule Board filters are also automatically populated with the vendor, subcontract, and subcontract line fields from the resource requirement. Because the requirement doesn't have any subcontract or subcontract line values filled in, these attributes are empty on the filter pane.
1. The system searches for resources that meet the filter criteria and lists them.
1. Update the **Worker type** field on the filter pane to **Contract Worker** to limit the search to contract workers. Update **Vendor** on the filter pane to select a vendor to limit the search to only show contract workers that belong to a specific vendor company.
1. Select a contract worker from the list and book the resource for the requirement.
1. A project team member is created. However, the project team member isn't updated with any subcontract or subcontract line and therefore the resource assignment isn't costed using the subcontract pricing. Manually update the project team member with a subcontract line and go to **Project Estimates** and select **Update prices** to see the updated cost of the resource assignment.

> [!NOTE]
> Project team members that have **Worker type** as **Contract worker** but don't have a subcontract reference are flagged as **Invalid** on the **Project team members** grid. If there are any project team members with this status, open the project team member record and manually update the subcontract and subcontract line fields so that the financial cost estimate accurately reflects the subcontractor cost on the **Estimates** tab.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
