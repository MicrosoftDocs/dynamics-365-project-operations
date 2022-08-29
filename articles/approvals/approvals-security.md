---
title: Security and Approvals
description: This article provides information about the security setup for working with approvals in Project Operations.
author: stsporen
ms.date: 08/29/2022
ms.topic: security
ms.reviewer: johnmichalak
ms.author: stsporen

---
# Security and Approvals

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

We include two roles for approving Time, Expense, Material entries
-	Project Approver
-	Project Approver Admin

## Project Approver
To approve project time, expense, or material entries you are required to have the correct permissions. These are demonstrated in the **Project Approver** security role, you are also required to have access to the relevant related entities such as Project, which can be assigned with **Project Manager** role. Additionally, to the role you are required to be a team member of the project and marked as an approver.

To approve non project entries, you are required to be the manager of the submitter.

## Project Approver Admin
NOTE: Project Approver Admin functionality requires the enablement of [Approval sets](./approvals/approval-sets) feature.

For scenarios which require users to bypass policies and allow for approval of entries across all projects, we include a special role **Project Approver Admin**, assigning this role will bypass the validation logic requiring team membership and being marked approver. Additional permissions required as listed in the **Project Approver** role.

SYSTEM user context bypasses validations in the same was that Project Approver Admin does.
