---
title: Actuals impact in a fixed price engagement
description: This article provides information about the impact on the Actuals table at various events during the lifecycle of a fixed price engagement in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.author: suvaidya
ms.date: 06/07/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Actuals impact in a fixed price engagement

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

The following table lists the actuals of different transaction types that are created at various events in a fixed price engagement.

| Event | Cost actual | Unbilled sales actual | Billed sales actual | Example |
|---|---|---|---|---|
| Time is created. | Not applicable | Not applicable | Not applicable | <p>Bob Kozack, from the Fabrikam US organizational unit that has a cost rate of 100 US dollars (USD 100) per hour, is working on a project that is named "Arm Installation at Adatum." This project is mapped to a fixed price billing method on the contract line. Here is a sample time entry from Bob Kozak:</p><p>Bob Kozack - 8 hours</p> |
| Time is submitted. | Not applicable | Not applicable | Not applicable | A cost journal line is created for the time entry. The default cost rate is entered in the journal entry. |
| The time entry is recalled before it's approved. | Not applicable | Not applicable | Not applicable | |
| Time is approved. | A cost actual is created. | Not applicable | Not applicable | <p>New actual that is created:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li></ul> |
| Time approval is canceled. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | Not applicable | Not applicable | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |
| The time entry is recalled after it's approved. | <p>The adjustment status of the original cost actual is updated to **Adjusted**.</p><p>A reversal cost actual is created that has an adjustment status of **Unadjustable**.</p> | Not applicable | Not applicable | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul> |
| The contract is confirmed. | <p>The adjustment status of the old cost actuals is updated to **Adjusted**.</p><p>Reversal cost actuals are created that have an adjustment status of **Unadjustable**.</p><p>New cost actuals are created after the contractual rules are reevaluated.</p> | Not applicable | Not applicable | <p>Existing actual that is updated:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800, *Adjusted*</li></ul><p>New actual that is created to reverse the previous financial impact:</p><ul><li>**Cost actual:** Bob Kozack, (8 hr), (USD 800), *Unadjustable*</li></ul><p>New actual that is created for the reevaluated financial impact:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li></ul> |
| An invoice is created. | Not applicable | Not applicable | Not applicable | |
| The invoice is confirmed with a milestone. | Not applicable | Not applicable | New milestone-based billed sales actuals are created. | <p>Existing actual that remains unchanged:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, USD 800</li></ul><p>New actual that is created to record the billed sales values:</p><ul><li>**Billed sales actual:** Milestone, USD 5,000</li></ul> |
| The invoice is corrected to credit the milestone. | Not applicable | Not applicable | Reversal billed sales actuals are created. | <p>Existing actual that remains unchanged:</p><ul><li>**Cost actual:** Bob Kozack, 8 hr, 800 USD</li></ul><p>Existing actual that is updated:</p><ul><li>**Billed sales actual:** Milestone, USD 5,000, *Adjusted*</li></ul><p>New actual that is created to reverse the previous billed sales values:</p><ul><li>**Billed sales actual:** Milestone, (USD 5,000),*Unadjustable*</li></ul> |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
