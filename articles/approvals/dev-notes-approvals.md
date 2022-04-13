---
title: Developer notes for Approvals
description: This topic provides additional developer information about working with approvals.
author: stsporen
ms.date: 11/09/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Developer notes for Approvals

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations includes validation logic that ensures correct record transition through the approval stages. Correct record transitions ensure: 

  - All supporting rows are created in related tables, such as journals and actuals.
  - The approver is marked as a **Project Approver** in the project before proceeding.


[!INCLUDE[footer-include](../includes/footer-banner.md)]