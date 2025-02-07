---
title: Process approvals programmatically
description: Learn how to use the msdyn_ProcessProjectApprovalSets API to approve records in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.date: 02/05/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Process approvals programmatically

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

Microsoft Dynamics 365 Project Operations provides the Process Project Approval Sets API. You can use this API to programmatically process approvals via Power Automate or a custom plug-in.

## Process Project Approval Sets API

### Name

msdyn\_ProcessProjectApprovalSets

### Input parameters

| Parameter        | Type              | Description |
|------------------|-------------------|-------------|
| ProjectApprovals | Entity Collection | A list of the project approval records to process. |
| ActionType       | Int               | <p>The action to perform on the records. The following options are available:</p><ul><li>Reject: 192350001</li><li>Approve: 192350003</li><li>Cancel: 192350004</li></ul> |
| NoteLogName      | String            | The note that you want to attach to the approval set. This note is shown in the **Logs** section. |

### Notes

- Different types of approvals (time, expense, or material) can be included in the `ProjectApprovals` entity collection.
- The specified action type is performed on all records in the entity collection. You can't perform a different action on a subset of the records. To approve some records and reject others, you must make two API calls and pass the appropriate `ActionType` value in each call.
- The approval process occurs in the context of the user who makes the request. Approval validations are run against that user (the `msdyn_Approver` field on the approval set).
- Approval sets are processed either synchronously or asynchronously, depending on the **Background Approval Threshold** value, just as in approvals that are done via the user interface (UI).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
