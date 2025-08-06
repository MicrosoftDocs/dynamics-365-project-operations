---
title: Actuals
description: This article provides information about how to work with actuals in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 06/05/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya

---

# Actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations Core_

Actuals represent the reviewed and approved financial and schedule progress on a project. Actuals are created when time, expense, and material usage entries, journal entries, and invoices are approved.

> [!IMPORTANT]
> **Actuals shouldn't be created or edited directly in the system**. New actuals can be created using entry journals [Creating actuals using entry journals](create-confirm-entry-journals.md) and existing actuals can be edited using correction journals [Correct actuals using correct entries](create-confirm-correction-journals.md). Microsoft Dynamics 365 Project Operations prevents deleting actuals from the system. This restriction preserves the financial integrity and any integration with other financial and accounting systems. Reversing, replacing, and editing actuals at various points in the business process lifecycle of your projects is supported using entry and correction journals. The only exceptions to this are the description and external description fields which remain editable.

## Recording actuals based on project events

Project Operations records the financial transactions that occur during a project engagement lifecycle as actuals. The creation of actuals at various events in the lifecycle varies, depending on whether the project engagement uses the time and materials billing model or the fixed price billing model, and whether it's in the presales stage or it's an internal project.

The following articles explain the impact on the Actuals table at various events for different variations:

- [Actuals impact in a time and materials engagement](ActualsonTM.md)
- [Actuals impact in a fixed price engagement](ActualonFP.md)
- [Actuals impact during the presales stage of an engagement](ActualonPreSales.md)
- [Actuals impact for an internal project](ActualonInternal.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
