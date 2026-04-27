---
title: Subcontracting options for project team members
description: Learn how to manage subcontracting for generic and staffed project team members in Dynamics 365. Explore options for creating or reserving subcontract lines.
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

- Create a new subcontract and add new lines to an existing subcontract for the selected project team members.
- Reserve against an existing subcontract and subcontract line.

You can choose from the available subcontracting options for generic project team members or choose from project team members that are staffed with a named resource who is a contract worker.

No subcontracting options are available for the following project team members:

- Project team members that are staffed with an employee.
- Project team members that are already associated with a subcontract and subcontract line.

## Subcontract an unstaffed project team member

To review and choose from the available subcontracting options for a generic or unstaffed project team member, follow these steps:

1. Select one or more project team members records where the resource is a generic resource.
1. Ensure that none of the selected project team member records are already subcontracted.
1. Select **Subcontracting options** on the project team members sub grid. The **Subcontracting options** dialog opens.
1. If you only selected one project team member record in step 1, the following options are available:
    - Create new subcontract lines.
    - Reserve against an existing subcontract.
   If you selected multiple project team member records in step 1, the only option available is to create new subcontract lines.
1. The option to reserve against an existing subcontract line allows you to select a subcontract and subcontract line that you want to reserve against. When selecting a subcontract line to reserve capacity, ensure that the subcontract line selected is for time and that the role required on the project team member matches the role that you purchased on the subcontract line.
1. When you select to create new subcontract lines for the project team members, the system prompts you to select the subcontract that you want to create these lines. The subcontract that you select to create new lines should be in **Draft** status. By using this option to create new subcontract lines for the selected project team members, the system creates one subcontract line for time for each project team member. The role, hours, and dates are copied from the project team member to each subcontract line that is created.
1. When you associate a generic team member with a subcontract and subcontract line, the system updates the **Worker type** field on the generic team member row to **Contract Worker** and sets the **Subcontract Validity** value to **Valid**.

## Subcontract a staffed project team member

You can view subcontracting options for a staffed project team member, as long as the staffed team member is a contract worker. To review and choose from the available subcontracting options for a staffed or named project team member, follow these steps:

1. Select one or more project team members records where the resource is a named contract worker.
1. Ensure that none of the project team member records are already subcontracted.
1. Select **Subcontracting options** on the project team members sub grid. The **Subcontracting options** dialog opens.
1. If you only selected one project team member record in step 1, the following options are available:
      - Create new subcontract lines.
      - Reserve against an existing subcontract.
  If you selected multiple project team member records in step 1, the only option available is to create new subcontract lines.
1. The option to reserve against an existing subcontract line allows you to select a subcontract and subcontract line that you want to reserve against. When selecting a subcontract line to reserve capacity, ensure the following:
      - The selected subcontract line is for time.
      - The role required on the project team member matches the role that you purchased on the subcontract line.
      - The vendor that the contract worker is associated to is the same as the vendor on the subcontract.
1. When you select to create new subcontract lines for the project team members, the system prompts you to select the subcontract that you want to create these lines. With this option, ensure that the vendor the contract worker belongs to is the same as the vendor on the subcontract.
1. The subcontract that you select to create new lines should be in **Draft** status. When you use this option to create new subcontract lines for the selected project team members, the system creates one subcontract line for time for each project team member. The role, hours, and dates are copied from the project team member to each subcontract line that is created.  
1. When a named team member is associated with a subcontract and subcontract line, the **Worker type** field on the named team member row is updated to **Contract Worker** and the **Subcontract Validity** value is set to **Valid**.

## Re-cost subcontractor assignments

When you link a project team member (generic or named) to subcontract lines by using the **Subcontracting options** dialog, the system re-costs any assignments to tasks that the team member has. The re-costing uses the purchase price list attached to the subcontract. On the **Estimates** tab on the **Project Details** page, select the **Update prices** button to see updated pricing and costing resulting from the decision to subcontract.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
