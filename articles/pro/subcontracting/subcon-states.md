---
title: State transitions on a subcontract
description: Learn how subcontract state transitions work in Microsoft Dynamics 365 Project Operations, from creation to closure, with clear lifecycle explanations.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# State transitions on a subcontract 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article explains the state transitions on a subcontract in Microsoft Dynamics 365 Project Operations. Each state is represented as either draft, confirmed, closed, or canceled. The following image represents the state transitions.

![Subcontract state model](../media/SubconStates.png)  

The following table provides a description of what each state represents in the lifecycle of a subcontract in Project Operations.

| State | Description | Allowed transitions |
| --- | --- | --- |
| Draft | This state represents the initial state of a subcontract. Negotiations with the vendor are in progress. The lines and pricing are subject to modifications. Use a subcontract in this state to estimate and staff project requirements for resources and materials. You can also reference it on time, expense, and material usage on a project. You can edit and delete a subcontract in this state. | Confirmed |
| Confirmed | This state represents the stage of a subcontract after negotiations with vendor on pricing and line items being purchased are complete. However, the actual delivery of materials and work by subcontracted resources is still ongoing. Use a subcontract in this state to estimate and staff project requirements for resources and materials. You can also reference it on time, expense, and material usage on a project. You can't edit or delete a subcontract in this state. Select **Cancel** to cancel a confirmed subcontract. Select **Re-open** to reopen the subcontract and bring it back into **Draft** status. Select **Close** to close a confirmed subcontract. | Closed <br> Canceled <br> Draft |
| Closed | This state represents the stage of a subcontract when actual delivery of materials and work by subcontracted resources is completed. You can no longer use a subcontract in this state to estimate and staff project requirements for resources and materials. Also, you can no longer reference it on time, expense, and material usage on a project. You can't edit or delete a subcontract in this state. | None |
| Canceled | This state represents the stage of a subcontract when actual delivery of materials and work by subcontracted resources is no longer needed. You can't use a subcontract in this state to estimate and staff project requirements for resources and materials. You also can't reference it on time, expense, and material usage on a project. You can't edit or delete a subcontract in this state. | None |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
