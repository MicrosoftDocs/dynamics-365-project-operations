---
title: Create or update actuals
description: Learn how to create or update actuals in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 02/28/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Create or update actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

As of Update Release (UR) 55, a back-end validation allows actuals to be created or updated only if a supported method is used, as described in this article.

If you try to use an unsupported method to create actuals, you might receive the following error message:

> The product doesn't support creating actuals either manually or through customizations. Use entry journals to create new actuals and Correct entries update existing actuals. More information is available at `https://aka.ms/EntryJournals`.

The validation **allows** the following scenarios:

- Create actuals from out-of-box actions.
- Create actuals via native Microsoft Dynamics 365 Project Operations APIs for supported business scenarios.
- Create or update actuals by using Power Automate flows that invoke the native Project Operations APIs in the Supported fields table later in this article.
- Create actuals via dual-write synchronization from finance and operations apps to Dataverse.
- Create actuals by using Data import jobs.
- Update custom fields on actuals.

The validation **blocks** the following scenarios:

- Create actuals from the user interface (UI).
- Manually create actuals in the maker portal.
- Create actuals by using JavaScript scripts.
- Create actuals by using plugins.

## Create new actuals

**You should not create new actuals directly in the system**. Instead, you can create actuals by using entry journals. Learn more in [Create and confirm Entry journals](create-confirm-entry-journals.md).

## Correct existing actuals

You can update existing actuals by selecting the **Correct entries** option in the billing backlog. The **Correct entries** option uses correction journals to allow for updates of some fields. Learn more in [Create and confirm Correction journals](create-confirm-correction-journals.md).

### Supported fields

The following table lists the out-of-box fields that can be updated on actuals. It also shows the allowed correction method for each field.

| Field | Allowed correction method |
|---|---| 
| Project | Correction journal |
| Task | Correction journal |
| Resource Role | Correction journal |
| Subcontract | Correction journal |
| Subcontract Line | Correction journal |
| Bookable Resource | Correction journal |
| Product | Correction journal |
| Write in Product | Correction journal |
| Start Date/Time | Correction journal |
| Document Date | Correction journal |
| Transaction Category | Correction journal |
| Billing Status | msdyn_MarkActualReadyToInvoiceOrNot API |
| Not-to-exceed Status | msdyn_ReevaluateActualNotToExceedStatus API |
| Revise | msdyn_revise API |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
