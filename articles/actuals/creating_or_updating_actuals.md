---
title: Creating or updating actuals
description: This article provides information about how to work with actuals in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.date: 02/25/2025
ms.topic: Creating or updating actuals
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya

---
# Creating or Updating Actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Commencing UR 55 release, a backend validation will prevent creates or updates to actuals that do not follow the allowed methods prescribed in ths page for this purpose. 

When attempting to create an Actual using an unsupported method, you may encounter the below error . 
" The product does not support creating actuals either manually or through customizations. Use entry journals to create new actuals and Correct entries update existing actuals. More information is available at https://aka.ms/EntryJournals."


## Scenarios blocked by this validation
1. Actuals created from user interface
3. Actuals created manually using maker portal
4. Actuals created using json scripts
   

## Scenarios not affected by this validation
1. Actuals created from synchronous OOB actions
2. Actuals created via supported scenarios through business rules
3. Actuals created or updated using Power automate flows that invoke native Project Operations API's listed in the table below.
4. Actuals created via Dual write sync from F&O to Dataverse
5. Updates made to custom fields on actuals
6. Acutals created using Data import jobs

      
# Creating new actuals
**Actuals shouldn't be created directly in the system**. New actuals can be created using entry journals [Creating actuals using entry journals](create-confirm-entry-journals.md) 

# Correcting existing Actuals
Existing actuals can be updated using **Correct entries** option on the billing backlog which uses correction journals to update certain fields.[Correct actuals using correct entries](create-confirm-correction-journals.md)


The List of OOB fields supported for update on actuals and their allowed correction method are listed in the following table.

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
| Revise | msdyn_revise |

