---
title: What's new March 2026 - Project Operations Core
description: Learn about quality updates that are available in the March 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 03/24/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new March 2026 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.165.3368.2

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals |**New Approvals Experience** <br><br> The UI for approvals is updated to live in a form with tabs for each type of approval record. Using this new UI, approvers can quickly see how many records of each type are pending their approval. This new UI also uses the time phased grid for time approvals, but is customizable to user's preferences| |
| Billing and Pricing |**Refund Retainers** <br><br> Project Operations now enables users to refund retainers associated with project contracts. Users can mark retainers as Ready for Refund, generate refund invoices, track refund status, and cancel refund requests prior to posting. Refund‑ready retainers are automatically included in refund invoices, helping streamline the return process and improve financial accuracy when managing customer advances.||
| Project Budgeting |**Enable improved project budgeting time phasing grid.** <br><br> With the improved Project Budget time‑phased grid, budget-line details are now displayed in a single row, with budget periods distributed based on configurations. This update provides a clear, more intuitive, and easier‑to‑analyze view of time‑phased budgets. All existing budget actions and states are fully supported. The feature is available behind the “Enable improved project budgeting time phasing grid” feature flag.| [Use time-phased project cost budget lines](../budget/time-phase-budget-line.md) |
| Sales |**What-if Analysis on Quotes** <br><br> What‑If Analysis in Dynamics 365 Project Operations allows users to model different staffing and pricing strategies, view real-time financial KPIs, and compare scenarios side by side—helping them apply the most profitable option directly to your project quote.| |
| Subcontracting |**Enabled Subcontracting UX improvements** <br><br> A new Hierarchy View is now available on the Subcontracts list page, enabling easier navigation across related subcontract data. This view presents Subcontracts, their associated subcontract lines, and the linked project in a clear hierarchical structure, making it simpler to understand relationships and move between related records. This enhancement is available behind the feature flag “Enable Subcontracting UX enhancements for smoother navigation and insights.”| [Enable improved subcontracting UX](../subcontracting/improved-sub-contracting-ui-experience.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference no.** | **Quality update** |
| --- | --- | --- |
|Approvals|	5918358|	Prevent recall of external expense entries|
|Approvals|	6114170|	Export to excel is not working for project approval entity after selecting the records|
|Billing and Pricing|	5519210|	Error when creating price override of type "At transaction cost"|
|Project And Resource Management|	6089066|	"Open in Project" is visible in environments where customizations are present|
|Sales|	6002415|	Quote line cost amount is wrong when cost-QLD is in different currency|
|Subcontracting|	5556498|	"An item with the same key has already been added" error when actuals linked to Vendor Invoice are re-evaluated during Contract confirmation|
|Time Entry|	6100760|	Time off entries do not appear on work hours calender when time entry of vacation or absence type is created on a working day|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
