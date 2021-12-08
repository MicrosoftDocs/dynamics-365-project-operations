---
title: State transitions for subcontract in Project Operations
description: This topic explains the state transistions on a Subcontract in Microsoft Dynamics 365 Project Operations as the subcontract is created, executed and closed.
author: rumant
ms.date: 12/03/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# State transitions for subcontract in Project Operations

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

The following picture represents the state transitions on a Subcontract in Project Operations:

![Subcontract state model](../media/SubconStates.png)  


The table below gives a description of what each state represents in the lifecycle of a Subcontract in Project Operations:

| State | Description | Allowed transitions |
| --- | --- | --- |
| Draft | This represents the initial state of Subcontract. Negotiations with the vendor are in progress. The lines and pricing are subject to modifications.A subcontract in this state can be used to estimate and staff project requirements for resources and materials. It can also be referenced on time, expense and material usage on a project.A subcontract in this state can be edited and deleted. | Confirmed |
| Confirmed | This represents the stage of Subcontract after negotiations with vendor on pricing and line items being purchased is complete. However, the actual delivery of materials and / or work by subcontracted resources is still ongoing. A subcontract in this state can be used to estimate and staff project requirements for resources and materials. It can also be referenced on time, expense and material usage on a project.A subcontract in this state cannot be edited or deleted. Use the Cancel button to cancel a confirmed subcontractUse the Re-open button to re-open the subcontract to bring it back into draft status.Use the Close button to close a confirmed subcontract | Closed <br> Cancelled <br> Draft |
| Closed | This represents the stage of Subcontract when actual delivery of materials and / or work by subcontracted resources is completed. A subcontract in this state can no longer be used to estimate and staff project requirements for resources and materials. Also it can no longer be referenced on time, expense and material usage on a project.A subcontract in this state cannot be edited or deleted. | None |
| Cancelled | This represents the stage of Subcontract when actual delivery of materials and / or work by subcontracted resources is no longer needed. A subcontract in this state cannot be used to estimate and staff project requirements for resources and materials or be referenced on time, expense and material usage on a project.A subcontract in this state cannot be edited or deleted. | None |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
