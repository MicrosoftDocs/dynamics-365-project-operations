---
title: Actuals impact for an internal project
description: This article provides information about the impact on the Actuals table at various events for an internal project in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.date: 01/09/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
ms.search.validFrom: 2020-10-01
---

# Actuals impact for an internal project

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Project Operations Core_

The following table lists the actuals of different transaction types that are created at various events in an internal project engagement.

| Event | Cost actual | Example |
|---|---|---|
| Time is created. | Not applicable | <p>Bob Kozack, from the Fabrikam US organizational unit that has a cost rate of 100 US dollars (USD 100) per hour, is working on a project that is named "Arm Installation at Adatum." This project is mapped to a fixed price billing method on the contract line. Here is a sample time entry from Bob Kozak:</p><p>Bob Kozack - 8 hours</p> |
| Time is submitted. | Not applicable | A cost journal line is created for the time entry. The default cost rate is entered in the journal entry. |
| The time entry is recalled before it's approved. | Not applicable | |
| Time is approved. | A cost actual is created. | <p>New actual that is created:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li></ul> |
| The time approval is canceled. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |
| The time entry is recalled after it's approved. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
