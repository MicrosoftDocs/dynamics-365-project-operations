---
title: Actuals impact during the presales stage of an engagement
description: This article provides information about the impact on the Actuals table at various events while an engagement is in the presales stage in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.date: 01/09/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
ms.search.validFrom: 2020-10-01
---

# Actuals impact during the presales stage of an engagement

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

The following table lists the actuals of different transaction types that are created at various events during the presales stage of a project engagement.

| Event | Cost actual | Example |
|---|---|---|
| Time is created. | Not applicable | <p>Bob Kozack, from the Fabrikam US organizational unit that has a cost rate of 100 US dollars (USD 100) per hour, is working on a project that is named "Arm Installation at Adatum." This project is mapped to a fixed price billing method on the contract line. For example, a time entry from Bob Kozak:</p><p>Bob Kozack - 8 hours</p> |
| Time is submitted. | Not applicable | A cost journal line is created for the time entry. The default cost rate is entered in the journal entry. |
| The time entry is recalled before it's approved. | Not applicable | |
| Time is approved. | A cost actual is created. | <p>New actual that is created:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li></ul> |
| Time approval is canceled. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |
| The time entry is recalled after it's approved. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |
| The quote is won, and a contract is created. | <p>The adjustment status of the old cost actuals is updated to **Adjusted**.</p><p>Reversal cost actuals are created that have an adjustment status of **Unadjustable**.</p><p>New cost actuals are created after the contractual rules are reevaluated.</p> | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul><p>New actuals that are created for the reevaluated financial impact when the quote is won and the contract is created:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li><li>**Unbilled sales actual:** Bob Kozack, 8 hr, USD 1,600</li></ul> |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
