---
# required metadata

title: Actuals
description: This article provides information about how to work with actuals in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 05/31/2022
ms.topic: overview
ms.custom: 
  - bap-template
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 

ms.assetid: 
ms.search.region: 
ms.search.industry: 
ms.author: rumant
ms.search.validFrom: 2020-10-01
---

# Actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Actuals represent the reviewed and approved financial and schedule progress on a project. They are created when time, expense, and material usage entries, journal entries, and invoices are approved.

> [!IMPORTANT]
> Actuals should not be edited or deleted from the system. Otherwise, financial integrity and any integration with other financial and accounting systems might be adversely affected. Microsoft Dynamics 365 Project Operations lets you use reversing and replacing actuals to edit actuals at various points in the business process lifecycle of your projects.

## Recording actuals based on project events

Project Operations records the financial transactions that occur during a project engagement lifecycle as actuals. The creation of actuals at various events in the lifecycle varies, depending on whether the project engagement uses the time and materials billing model or the fixed price billing model, and whether it's in the pre-sales stage or it's an internal project.

The following articles explain the impact on the Actuals table at various events for different variations:

- [Actuals impact in a time and materials engagement](ActualsonTM.md)
- [Actuals impact in a fixed price engagement](ActualonFP.md)
- [Actuals impact during the pre-sales stage of an engagement](ActualonPreSales.md)
- [Actuals impact for an internal project](ActualonInternal.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
