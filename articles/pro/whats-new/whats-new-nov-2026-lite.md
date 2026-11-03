---
title: What's new November 2026 - Project Operations Core
description: Learn about quality updates that are available in the November 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 11/03/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new November 2026 - Project Operations Core

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

> [!IMPORTANT]
> Starting with version 4.173, Dynamics 365 Project Operations introduces updated version numbering for official solution releases. The four-part format remains unchanged, but date-based build numbering is replaced with a controlled build number and an automatically increasing revision—for example, 4.173.1.38. Solution and package versions remain aligned, while separate version ranges for official releases and corresponding validation builds help prevent downgrade-related upgrade conflicts in test environments. This **change affects version numbering only** and doesn't alter application functionality.

- Project Operations in a Microsoft Dataverse environment version 4.173.1.38.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals Agent | **Policy Authoring Assistant** <br><br> This feature introduces an agent that assists users with authoring policy documents for the Activity Approvals Agent in project operations. This agent reviews a policy document and provides feedback on changes that help increase the accuracy and reliability of the activity approvals agent. | |
| Project Management | **Task grid full screen mode** <br><br> You can now expand the task grid to full screen, giving you a larger, more immersive workspace. You can view more tasks at once with more detail visible per task, so you can review, and manage project information. This feature is especially useful for large schedules, where seeing more of the plan at a glance makes it easier to spot dependencies and keep the project on track. | |
| Project Management | **Calendar control upgrade** <br><br> We're upgrading the calendar control used in project calendar, resource calendar, and calendar templates to V2. This upgrade resolves known accessibility issues, so users who rely on keyboard navigation, screen readers, and other assistive technologies get a more consistent and inclusive experience. | |
| Project Management | **Team member grid upgrade** <br><br> We're upgrading the team member grid to OneGrid, the latest platform-supported grid, replacing the older grid that isn't supported. This upgrade resolves existing accessibility issues, so users who rely on keyboard navigation, screen readers, and other assistive technologies get a more consistent and inclusive experience when viewing and managing team members. | |
| Time Entry | **Add Weekly Time Entry Notes** <br><br> When the new Weekly Time Entry Notes preview feature is enabled, time entry users can view and edit Description and External Comment fields for multiple time entries in a week. For ease of reference, these fields are referred to as "Notes." | [Weekly Time Entry Notes](../../time/ui-behavior-time.md#edit-descriptions-and-external-comments-for-a-week-preview) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing | 6575256 | You can pull the same Project Contract Retainer into multiple Draft Invoices after you refresh Invoice Line Transactions. |
| Billing | 6616961 | Time zone-agnostic milestone date doesn't correctly flow to billed sales actuals. |
| Billing | 6719787 | Invoice Line Detail form has no link back to the Project Contract Line Milestone that created it. |
| Billing | 6748294 | Can't invoice unbilled sales actuals that don't have Project Contract Line Customer from billing hub Actuals form. |
| Infra | 6676884 | Deleting a ProjectContractLineTask creates duplicate unbilled-sales Actual records. |
| Pricing | 6437867 | Import from Project estimate should only use transaction connections as a fallback. |
| Pricing | 6501273 | Pricing engine uses caller context instead of system service for price list reads on Material/Expense creation. |
| Project Estimates | 6293835 | Sales price at transaction cost doesn't show in project estimates when cost and sales currency differ. |
| Project Estimates | 6733012 | Expense/Material estimate sales price ignores quote price list when project is linked to multiple quote lines. |
| Sales | 6576461 | Block Quantity updates on Quote/Contract/Invoice lines to prevent reporting discrepancies. |
| Sales | 6630658 | Milestones can only be deleted from the context of an OrderLine form. |
| Sales | 6680992 | Error blocks quote revision when the Quote has no header split billing rule. |
| Sales | 6713001 | Quote with multiple customers can't be Closed as won or revised after merging its customer accounts. |
| Sales | 6720867 | Preventing duplicate reversal connections after invoice revision. |
| Sales | 6728380 | Revising work-based quote linked to Sales Hub item-based opportunity drops split-billing rules. |
| Subcontracting | 6675993 | Deletion of Vendor Invoice Lines bypasses read-only validation for In Progress/Complete verified invoice lines. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
