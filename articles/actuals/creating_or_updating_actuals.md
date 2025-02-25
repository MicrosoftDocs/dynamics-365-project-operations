---
title: Actuals
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

Commencing UR 55 release, a backend validation will prevent creates or updates to actuals that do not follow the methods prescribed in ths page for creation or correction of actuals. 

When attempting to manually create an Actual, you may encounter the below error . 
" The product does not support creating actuals either manually or through customizations. Use entry journals to create new actuals and Correct entries update existing actuals. More information is available at https://aka.ms/EntryJournals."

## The following scenarios are blocked with this validation
1. Acutals created using Data import jobs
2. Actuals created manually
3. 



## Validation does not apply to the following scenarios
1. Updates made to custom fields on actuals
2. Actuals created or updated using Power automate flows that invoke native Project Operations API's listed in the table below.
   

## Creating new actuals
**Actuals shouldn't be created directly in the system**. New actuals can be created using entry journals [Creating actuals using entry journals](create-confirm-entry-journals.md) 

## Correcting existing Actuals
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

