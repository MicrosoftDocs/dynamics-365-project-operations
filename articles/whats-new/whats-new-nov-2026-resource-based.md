---
title: What's new November 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the November 2026 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 11/03/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new November 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

> [!IMPORTANT]
> Starting with version 4.173, Dynamics 365 Project Operations introduces updated version numbering for official solution releases. The four-part format remains unchanged, but date-based build numbering is replaced with a controlled build number and an automatically increasing revision—for example, 4.173.1.38. Solution and package versions remain aligned, while separate version ranges for official releases and corresponding validation builds help prevent downgrade-related upgrade conflicts in test environments. This **change affects version numbering only** and doesn't alter application functionality.

- Project Operations in a Microsoft Dataverse environment version 4.173.1.38.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.49.

## Project Operations dual-write map updates

The Project Operations November 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals Agent | **Policy Authoring Assistant** <br><br> This feature introduces an agent that helps you author policy documents for the Activity Approvals Agent in project operations. The agent reviews a policy document and provides feedback on changes that help increase the accuracy and reliability of the activity approvals agent. | |
| Project Management | **Task grid full screen mode** <br><br> You can now expand the task grid to full screen, giving you a larger, more immersive workspace. You can view more tasks at once with more detail visible per task, so you can review, and manage project information. This feature is especially useful for large schedules, where seeing more of the plan at a glance makes it easier to spot dependencies and keep the project on track. | |
| Project Management | **Calendar control upgrade** <br><br> We're upgrading the calendar control used in project calendar, resource calendar, and calendar templates to V2. This upgrade resolves known accessibility issues, so users who rely on keyboard navigation, screen readers, and other assistive technologies get a more consistent and inclusive experience. | |
| Project Management | **Team member grid upgrade** <br><br> We're upgrading the team member grid to OneGrid, the latest platform-supported grid, replacing the older grid that isn't supported. This upgrade resolves existing accessibility issues, so users who rely on keyboard navigation, screen readers, and other assistive technologies get a more consistent and inclusive experience when viewing and managing team members. | |
| Time Entry | **Add Weekly Time Entry Notes** <br><br> The new Weekly Time Entry Notes preview feature enables time entry users to view and edit Description and External Comment fields for multiple time entries in a week. For ease of reference, the feature refers to these fields as "Notes." | [Weekly Time Entry Notes](..//time/ui-behavior-time.md#edit-descriptions-and-external-comments-for-a-week-preview) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Actuals | 6791609 | Accounting-transactions dual-write blocks integration journal posting. |
| Billing | 6575256 | Same Project Contract Retainer can be pulled into multiple Draft Invoices after Refresh Invoice Line Transactions. |
| Billing | 6616961 | Time Zone Agnostic Milestone Date doesn't correctly flow to Billed Sales actuals. |
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

## Project management and accounting in Finance

For information about the bug fixes that this update includes, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1156136&dbType=3&qc=40dd639253c871684fa1bcc4740fa3b1ee0e59f724196d6c4e76c35ce03a5876).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
