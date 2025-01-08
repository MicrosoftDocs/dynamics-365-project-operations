---
title: Security and approvals
description: This article provides information about the security setup for working with approvals in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 08/29/2022
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya

---
# Security and approvals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations uses two security roles to allow for the approval of time, expense, and material entries:

- Project Approver
- Project Approver Admin

## Project Approver

You must have the **Project Approver** security role to approve project time, expense, and material entries. You must also have access to the relevant related entities, such as **Project**. That access can be assigned by someone who has the **Project Manager** role. Additionally, you must be a team member of the project and marked as an approver.

To approve non-project entries, you must be the manager of the submitter.

## Project Approver Admin

> [!NOTE]
> The [Approval sets](approval-sets.md) feature must be enabled before you can use the Project Approver Admin functionality.

The **Project Approver Admin** security role allows users to bypass policies and allows for the approval of entries across all projects. Assignment of this role will bypass the validation logic that requires team membership and being marked as an approver. You must have access to the relevant related tables, such as **Project**, via security roles assigned to you.

The SYSTEM user context bypasses validations in the same way as the Project Approver Admin security role.
