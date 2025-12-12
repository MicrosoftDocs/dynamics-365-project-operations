---
title: Security and approvals
description: This article provides information about the security setup for working with approvals in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.date: 02/10/2025
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti

---
# Security and approvals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations has different requirements for approving time, material, and expense entries based on if the entry is linked to a project or not.

## Requirements for approving time, material, and expense entries linked to projects

In order to approve project time, expense, and material entries linked to a project, a user must be a team member on the project and have the **Project Approver** field on their team member record set to yes. They must also have access to the relevant related entities, such as **Project**. The **Project Approver** role grants a user the required entity permissions in Dataverse to approve records of any type.

## Approving time, material, and expense entries linked to projects

To approve nonproject entries, the approving user must be the [manager](/dynamics365/customerengagement/on-premises/developer/entities/systemuser?view=op-9-1#BKMK_ParentSystemUserId) of the submitter.

## Project Approver Admin

The **Project Approver Admin** security role allows users to bypass policies and allows for the approval of all entries regardless of type or if it's linked to a project. Assignment of this role bypasses the validation logic that requires team membership and being marked as an approver or status as the submitting user's manager. You must have access to the relevant related tables, such as **Project**, via security roles assigned to you.

The SYSTEM user context bypasses validations in the same way as the Project Approver Admin security role.
