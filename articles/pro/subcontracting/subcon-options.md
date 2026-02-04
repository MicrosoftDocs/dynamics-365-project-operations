---
title: Subcontracting options for project team members
description: This article explains the subcontracting options for project team members in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontracting options for project team members

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

In Microsoft Dynamics 365 Project Operations, you can evaluate the subcontracting options available for one or more project team members. The available subcontracting options allow you to:

- Create a new subcontract and/or create new lines on an existing subcontract for the selected project team members.
- Reserve against an already existing subcontract and subcontract line.

You can choose from the available subcontracting options for generic project team members or choose from project team members that have been staffed with a named resource that is a contract worker.

There are no subcontracting options available for the following:

- Project team members that have been staffed with an employee.
- Project team members that are already associated to a subcontract and subcontract line.

## Subcontracting an unstaffed project team member

To review and choose from the available subcontracting options for a generic or unstaffed project team member, follow these steps:

1. Select one or more project team member records where the resource is a generic resource.
2. Ensure that none of the selected project team member records are already subcontracted.
3. Select **Subcontracting options** on the project team members sub grid. The **Subcontracting options** dialog opens.
4. If you only selected one project team member record in step 1, then the following options will be available:
    - Create new subcontract lines.
    - Reserve against an existing subcontract
   If you selected multiple project team member records in step 1, then the only option available is to create a new subcontract lines.
5. The option to reserve against an existing subcontract line allows you to select a subcontract and subcontract line that you want to reserve against. When selecting a subcontract line to reserve capacity, you should ensure that the subcontract line selected is for time and that the role required on the project team member matches the role that was purchased on the subcontract line.
6. When you select to create new subcontract lines for the project team members, the system will allow you to select the subcontract that you want to create these lines. The subcontract that you select to create new lines in should be in **Draft** status. With this option to create new subcontract lines for the selected project team members, the system will create one subcontract line for time for each project team member. The role, hours, and dates will be copied from the project team member to each subcontract line that is created.
7. When a generic team member is associated with a subcontract and subcontract line, the **Worker type** field on the generic team member row will be updated to **Contract Worker** and the **Subcontract Validity** value will be set to **Valid**.

## Subcontracting a staffed project team member

Like generic or unstaffed team members, you can also view subcontracting options for a staffed project team member as long as the staffed team member is a contract worker. To review and choose from the available subcontracting options for a staffed or named project team member, follow these steps:

1. Select one or more project team member records where the resource is a named contract worker.
2. Ensure that none of the project team member records selected are already subcontracted.
3. Select **Subcontracting options** on the project team members sub grid. The **Subcontracting options** dialog opens.
4. If you only selected one project team member record in step 1, then the following options will be available:
      - Create new subcontract lines.
      - Reserve against an existing subcontract.
  If you selected multiple project team member records in step 1, then the only option available is to create a new subcontract lines.
5. The option to reserve against an existing subcontract line allows you to select a subcontract and subcontract line that you want to reserve against. When selecting a subcontract line to reserve capacity, you should ensure the following:
      - The selected subcontract line is for time.
      - The role required on the project team member matches the role that was purchased on the subcontract line.
      - The vendor that the contract worker is associated to is the same as the vendor on the subcontract.
6. When you select to create new subcontract lines for the project team members, the system will allow you to select the subcontract that you want to create these lines. With this option, you should ensure that the vendor the contract worker belongs to is the same as the vendor on the subcontract.
7. The subcontract that you select to create new lines in should be in **Draft** status. With this option to create new subcontract lines for the selected project team members, the system will create one subcontract line for time for each project team member. The role, hours, and dates will be copied from the project team member to each subcontract line that is created.  
8. When a named team member is associated with a subcontract and subcontract line, the **Worker type** field on the named team member row will be updated to **Contract Worker** and the **Subcontract Validity** value will be set to **Valid**.

## Re-costing subcontractor assignments

When a project team member (generic or named) is linked to subcontract lines using the **Subcontracting options** dialog, any assignments to tasks that the team member has will be re-costed based on the purchase price list attached to the subcontract. On the **Estimates** tab on the **Project Details** page, select the **Update prices** button to see updated pricing and/or costing resulting from the decision to subcontract.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
