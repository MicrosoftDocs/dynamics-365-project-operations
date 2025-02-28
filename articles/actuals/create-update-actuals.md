---
title: Create or update actuals
description: Learn about how to create or update actuals in Microsoft Dynamics 365 Project Operations.
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

Beginning in the UR 55 release, a backend validation that prevents creating or updating actuals that don't follow the allowed methods prescribed on this page. 

When attempting to create an actual using an unsupported method, you may receive the following error: 

   **The product doesn't support creating actuals either manually or through customizations. Use entry journals to create new actuals and Correct entries update existing actuals. More information is available at https://aka.ms/EntryJournals.**


The validation _allows_ the following scenarios:

- Actuals created from out-of-the-box (OOB) actions.
- Actuals created via native project operations APIs for supported business scenarios.
- Actuals created or updated using Power Automate flows that invoke native Project Operations APIs listed in the following table below.
- Actuals created via Dual-write sync from finance and operations apps to Dataverse.
- Actuals created using Data import jobs.
- Updates made to custom fields on actuals.

The validation _blocks_ the following scenarios:

- Actuals created from user interface.
- Actuals created manually using maker portal.
- Actuals created using JavaScript scripts.
- Actuals created using plugins.
        
## Create new actuals

**Actuals shouldn't be created directly in the system**. New actuals can be created using entry journals. Learn more in [Creating actuals using entry journals](create-confirm-entry-journals.md). 

## Correct existing Actuals

Existing actuals can be updated using the **Correct entries** option on the billing backlog. **Correct entries** uses correction journals to allow updates on some fields. Learn more in [Correct actuals using correct entries](create-confirm-correction-journals.md).

### Supported fields

The OOB fields that are supported for updates on actuals and their allowed correction method are listed in the following table.

| Field | Correction Method |
|---|---| 
| Project | Correction Journal |
| Task | Correction Journal |
| Resource Role | Correction Journal |
| Subcontract | Correction Journal |
| Subcontract Line | Correction Journal |
| Bookable Resource | Correction Journal |
| Product | Correction Journal |
| Write in Product | Correction Journal |
| Start Date/Time | Correction Journal |
| Document Date | Correction Journal |
| Transaction Category | Correction Journal |
| Billing Status | msdyn_MarkActualReadyToInvoiceOrNot API |
| Not-to-exceed Status | msdyn_ReevaluateActualNotToExceedStatus API |
| Revise | msdyn_revise API |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
