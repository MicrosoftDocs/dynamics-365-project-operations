---
title: Process approvals programmatically
description: Learn how to use the msdyn_ProcessProjectApprovalSets API to approve records in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.date: 05/07/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Process approvals programmatically

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Microsoft Dynamics 365 Project Operations provides the Process Project Approval Sets API. Use this API to programmatically process approvals through Power Automate or a custom plug-in.

## Process Project Approval Sets API

### Name

msdyn\_ProcessProjectApprovalSets

### Input parameters

| Parameter        | Type              | Description |
|------------------|-------------------|-------------|
| ProjectApprovals | Entity Collection | A list of the project approval records to process. |
| ActionType       | Int               | <p>The action to perform on the records. The following options are available:</p><ul><li>Reject: 192350001</li><li>Approve: 192350003</li><li>Cancel: 192350004</li></ul> |
| NoteLogName      | String            | The note that you want to attach to the approval set. This note appears in the **Logs** section. |

### Notes

- Include different types of approvals (time, expense, or material) in the `ProjectApprovals` entity collection.
- The specified action type applies to all records in the entity collection. You can't perform a different action on a subset of the records. To approve some records and reject others, make two API calls and pass the appropriate `ActionType` value in each call.
- The approval process occurs in the context of the user who makes the request. The system runs approval validations against that user (the `msdyn_Approver` field on the approval set).
- As with approvals done through the user interface (UI), the system processes approval sets either synchronously or asynchronously, depending on the **Background Approval Threshold** value.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
