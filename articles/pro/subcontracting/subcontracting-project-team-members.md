---
title: Subcontracting project team members
description: This article explains how to subcontract project team members in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 12/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontracting project team members

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

In Microsoft Dynamics 365 Project Operations, you can choose to subcontract unstaffed or staffed project team members.

- Unstaffed project team members have a generic resource assigned.
- Staffed team members have a named resource assigned.

When you link a project team member to a subcontract line, any assignments to tasks that the team member has will be recosted based on the purchase price list attached to the subcontract.  On the **Estimates** tab on the **Project Details** page, select the **Update prices** button to see updated pricing and/or costing resulting from the decision to subcontract. 

## Subcontracting an unstaffed project team member
The **Team Member details** page has subcontract and subcontract line fields that allow a project manager to express how they would like to draw the capacity required from a subcontract. To subcontract a project team member as a generic resource, follow these steps:

1.	Choose a subcontract on the **Team member detail** page.

2.	You can only select subcontracts with **Draft** or **Confirmed** status. **Closed** or **Canceled** subcontracts cannot be selected. 

3.	The **Subcontract line** field becomes visible after you select a subcontract.

4.	In the **Subcontract line** field, you can only select subcontract lines that are for time. You cannot select subcontract lines for expense or material.

5.	The role for the project team member record needs to match the role on the subcontract line. This ensures that the time for the role that is being estimated on the project is the same role that is purchased on the subcontract line. 

When a generic team member is associated with a subcontract and subcontract line, the **Worker type** field on the generic team member row will be updated to **Contract Worker** and **Subcontract Validity** will be set to **Valid**.

## Subcontracting a staffed project team member
Like generic or unstaffed team members, staffed team member capacity required on a project can also be linked to a subcontract. To subcontract a named project team member, follow these steps:

1.	Make sure that the named resource is set up as a contract worker type of bookable resource. Also, make sure that the **Vendor** field on the bookable resource matches the vendor on the subcontract that you are selecting. 

2.	You can only select subcontracts in **Draft** or **Confirmed** status. **Closed** or **Canceled** subcontracts cannot be selected. 

3.	The **Subcontract line** field becomes visible after you select a subcontract.

4.	In the **Subcontract line** field, you can only select subcontract lines that are for time. You cannot select subcontract lines for expense or material.

5.	The role for the project team member record needs to match the role on the subcontract line. This ensures that the time for the role that is being estimated on the project is the same role that is purchased on the subcontract line. 

Named project team members that are set up as a contract worker type of **Bookable resource** will be show with a subcontract validity status of **Not valid** if they are not linked with a subcontract. When a named project team member is associated with a subcontract and subcontract line, the **Worker type** field in the team member row will update to **Contract Worker** and **Subcontract Validity** will be set to **Valid**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
