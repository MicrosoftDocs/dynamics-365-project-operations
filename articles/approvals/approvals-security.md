---
title: Security and approvals
description: This article provides information about the security setup for working with approvals in Project Operations.
author: stsporen
ms.date: 08/29/2022
ms.topic: security
ms.reviewer: johnmichalak
ms.author: stsporen

---
# Security and approvals

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project Operations uses two security roles to allow approving time, expense, and material entries:
-	Project Approver
-	Project Approver Admin

## Project Approver
The **Project Approver** security role is required for you to have the ability to approve project time, expenses, and material entries. You must also have access to the relevant related entities, such as **Project**, which can be assigned by someone with the **Project Manager** role. Additionally, you're required to be a team member of the project and marked as an approver.

To approve non-project entries, you are required to be the manager of the submitter.

## Project Approver Admin

> [!NOTE]
> The [Approval sets](approval-sets.md) feature must be enabled to use the Project Approver Admin functionality.

The **Project Approver Admin** security role allows users to bypass policies and allow for approval of entries across all projects. Assigning this role will bypass the validation logic that requires team membership and being marked approver. You must have access to the relevant related entities, such as **Project**, which can be assigned by someone with the **Project Manager** role.

The SYSTEM user context bypasses validations in the same way that Project Approver Admin does.
