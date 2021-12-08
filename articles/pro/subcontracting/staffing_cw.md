---
title: Staffing a project with contract workers and subcontracted capacity
description: This topic explains how project requirements can be staffed using contract workers or subcontracted capacity in Project Operations.
author: rumant
ms.date: 12/03/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Staffing a project with contract workers and subcontracted capacity

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Generic project team members can be staffed with Employees or Contract Workers. When staffing a project with contract workers, you can limit your staffing options to specific contract workers that are assigned to a subcontract line. 
To search for and staff resource requirements with contract workers that belong to a specific subcontract line, follow these steps:

1. Create a generic project team member that references a subcontract and subcontract line.
2. Generate a resource requirement for this generic project team member using button on the project team members sub grid called “Generate requirement”
3. Select the team member row and click on the “Book” button on the sub grid. 
4. This opens the Schedule Board with the requirement context. Along with other attributes such as dates, role, Organizational unit fields, the Schedule board filters are also automatically populated with the vendor, subcontract, and subcontract line fields from the resource requirement.
5. The system searches for resources that meet the filter criteria and lists them. 
6. Select one of the filtered resources and book the resource for the requirement. 
7. Project team member is created and updated with subcontract and subcontract line reference.  Navigate to Project Estimates and click on update prices to see the updated cost of the resource assignment. 

> [!NOTE]
> Updating the project team member with a subcontract and subcontract line reference may not always be possible during the booking if the resource is assigned to multiple subcontract lines. If the system is unable to update the project team member with a subcontract and subcontract line, then open the project team member record and manually update these fields so that the financial cost estimate accurately reflects the subcontractor cost.

To search for and staff resource requirements with any contract worker, follow these steps:

1. Create a generic project team member.
2. Generate a resource requirement for this generic project team member using button on the project team members sub grid called “Generate requirement”
3. Select the team member row and click on the “Book” button on the sub grid. 
4. This opens the Schedule Board with the requirement context. Along with other attributes such as dates, role, Organizational unit fields, the Schedule board filters are also automatically populated with the vendor, subcontract, and subcontract line fields from the resource requirement. Since the requirement did not have any subcontract or subcontract line values filled, these attributes will be empty on the filter pane
5. The system searches for resources that meet the filter criteria and lists them. 
6. Update Worker type field on the filter pane to ‘Contract Worker’ to limit the search to contract workers. Update vendor on the filter pane to select a Vendor to limit the search to only show contract workers that belong to a specific vendor company. 
7. Select a contract worker from ones listed and book the resource for the requirement.
8. Project team member is created. However, the project team member is not updated with any subcontract or subcontract line and therefore the resource assignment will not be costed using the subcontract pricing. Manually update the project team member with a subcontract line and navigate to Project Estimates and click on update prices to see the updated cost of the resource assignment. 

> [!NOTE]
> Project team members that have “Worker type” as “Contract worker” but do not have a subcontract reference are flagged as “Invalid” on the “Project team members” grid. When you see any project team members with this status, open the project team member record and manually update the subcontract and subcontract line fields so that the financial cost estimate accurately reflects the subcontractor cost on the Estimates tab. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
