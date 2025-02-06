---
title: Process approvals programmatically
description: This article provides information about how to use the msdyn_ProcessProjectApprovalSets API to approve records in Project Operations
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

Microsoft Dynamics 365 Project Operations provides the Process Project Approval Sets API to programmatically process approvals via Power Automate or custom plugin.

## Process Project Approval Sets API

### Name

msdyn\_ProcessProjectApprovalSets

### Input Parameters

| Parameter                | Type              | Description                                                                                                    |
|--------------------------|-------------------|----------------------------------------------------------------------------------------------------------------|
| ProjectApprovals         | Entity Collection | A list of project approval records to process                                                                  |
| ActionType               | Int               | The action to perform on the given records (Options: Reject: 192350001, Approve: 192350003, Cancel: 192350004) |
| NoteLogName              | String            | The note that you want attached to the approval set, which will be visible in the “Logs” section               |

### Additional notes

- Different types of approvals (time, expense, or material) may be included in the ProjectApprovals Entity Collection
- The specified ActionType will be performed on all records in the entity collection. There is no option to perform different actions on a subset of the included records. To approve some records and reject others, two calls of the API are required with the appropriate ActionType passed for each call
- The approval process happens in the context of the user who makes the request, and approval validations are run against that user (field msdyn_Approver on the approval set)
- Approval sets are then processed synchronously or asynchronously according to the Background Approval Threshold in the same manner as approvals done via the UI


[!INCLUDE[footer-include](../includes/footer-banner.md)]
