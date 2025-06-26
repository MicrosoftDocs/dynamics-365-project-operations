---
title: What's new October 2021 - Project Operations Core deployment
description: This article provides information about the quality updates available in the October 2021 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new October 2021 - Project Operations Core deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Microsoft Dataverse environment version 4.25.0.91


## Features included in this release

The following features are included in this release:

[Subcontract management](../subcontracting/managing-subcontracts-overview.md): This feature provides the ability to create a subcontract with the vendor, itemize all purchases as line items on the subcontract, adjust pricing, and associate contacts.


## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2209402 | Corrected the validations that were preventing retainer amounts from being invoiced when a project contract is confirmed. |
| Opportunity management | 2227414 | The **Product**, **Write- In**, and **IsProductOverriden** fields are copied to the quote line details and contract line details. |
| Billing and pricing | 2338357 | The currency on the material usage log must default from the project's currency when the project is selected. |
| Time and expense | 2414777 | Canceling an approval when the expense or time entry has more than one associated project approval must be possible. |
