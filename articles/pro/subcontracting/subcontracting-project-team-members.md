---
title: Subcontracting project team members
description: Learn how to subcontract project team members in Microsoft Dynamics 365 Project Operations. Follow step-by-step instructions for both unstaffed and staffed resources.
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

When you link a project team member to a subcontract line, the system recosts any assignments to tasks that the team member has based on the purchase price list attached to the subcontract. On the **Estimates** tab on the **Project Details** page, select the **Update prices** button to see updated pricing and costing resulting from the decision to subcontract.

## Subcontracting an unstaffed project team member

The **Team Member details** page has subcontract and subcontract line fields that allow a project manager to specify how they want to draw the capacity required from a subcontract. To subcontract a project team member as a generic resource, follow these steps:

1. Choose a subcontract on the **Team member detail** page.
1. Select only subcontracts with **Draft** or **Confirmed** status. You can't select **Closed** or **Canceled** subcontracts.
1. After you select a subcontract, the **Subcontract line** field becomes visible.
1. In the **Subcontract line** field, select only subcontract lines that are for time. You can't select subcontract lines for expense or material.
1. The role for the project team member record needs to match the role on the subcontract line. This requirement ensures that the time for the role that's being estimated on the project is the same role that the system purchases on the subcontract line.

When you associate a generic team member with a subcontract and subcontract line, the system updates the **Worker type** field on the generic team member row to **Contract Worker** and sets **Subcontract Validity** to **Valid**.

## Subcontracting a staffed project team member

You can link staffed team member capacity required on a project to a subcontract, just like generic or unstaffed team members. To subcontract a named project team member, follow these steps:

1. Set up the named resource as a contract worker type of bookable resource. Also, make sure that the **Vendor** field on the bookable resource matches the vendor on the subcontract that you select.
1. Select subcontracts in **Draft** or **Confirmed** status. You can't select **Closed** or **Canceled** subcontracts.
1. After you select a subcontract, the **Subcontract line** field becomes visible.
1. In the **Subcontract line** field, select only subcontract lines that are for time. You can't select subcontract lines for expense or material.
1. The role for the project team member record needs to match the role on the subcontract line. This requirement ensures that the time for the role that's being estimated on the project is the same role that the system purchases on the subcontract line.

If you set up named project team members as a contract worker type of **Bookable resource** and don't link them with a subcontract, they show a subcontract validity status of **Not valid**. When you associate a named project team member with a subcontract and subcontract line, the **Worker type** field in the team member row updates to **Contract Worker** and **Subcontract Validity** is set to **Valid**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
