---
title: What's new March 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the March 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 03/24/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new March 2026 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.165.3368.2.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.47.

# Project Operations dual-write map updates

This release doesn't include updates for Project Operations dual-write maps. For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Approvals |**New Approvals Experience** <br><br> The UI for approvals has been updated to live in a form with tabs for each type of approval record. Using this new UI, approvers can quickly see how many records of each type are pending their approval. This new UI also uses the time phased grid for time approvals, but is customizable to user's preferences| |
| Billing and Pricing |**Refund Retainers** <br><br> Project Operations now enables users to refund retainers associated with project contracts. Users can mark retainers as Ready for Refund, generate refund invoices, track refund status, and cancel refund requests prior to posting. Refund‑ready retainers are automatically included in refund invoices, helping streamline the return process and improve financial accuracy when managing customer advances.| |
| Project Budgeting |**Enable improved project budgeting time phasing grid.** <br><br> With the improved Project Budget time‑phased grid, budget line details are now displayed in a single row, with budget periods distributed across the same row based on the configured budget periods. This provides a clearer, more intuitive, and easier‑to‑analyze view of time‑phased budgets. All existing budget actions and states are fully supported. The feature is available behind the “Enable improved project budgeting time phasing grid” feature flag.| || Subcontracting |**Enabled Subcontracting UX improvements** <br><br> A new Hierarchy View is now available on the Subcontracts list page, enabling easier navigation across related subcontract data. This view presents Subcontracts, their associated subcontract lines, and the linked project in a clear hierarchical structure, making it simpler to understand relationships and move between related records. This enhancement is available behind the feature flag “Enable Subcontracting UX enhancements for smoother navigation and insights.”| |
| Project Financials |**Enable editing of due date for project invoices** <br><br> Allows users to manually edit the due date on project invoice proposals, providing flexibility to align payment terms with customer agreements independent of automatically calculated dates.| |
| Project Financials |**Enable selective import from staging for invoice proposals** <br><br> This feature streamlines population of project invoice proposal lines when users don't want to wait for the scheduled staging process to run. A new "Import lines" button on the project invoice proposals screen allows selective import rather than a full batch run.| |
| Project Financials |**Use the modern architecture for existing legal entities with project data** <br><br> Additional scenarios were added to the feature to support sales orders, item requirements, and sales agreements in existing PMA projects.| |
| Sales |**What-if Analysis on Quotes** <br><br> What‑If Analysis in Dynamics 365 Project Operations allows users to model different staffing and pricing strategies, view real-time financial KPIs, and compare scenarios side by side—helping them apply the most profitable option directly to your project quote.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
|Approvals|	5918358|	Prevent recall of external expense entries|
|Approvals|	6114170|	Export to excel is not working for project approval entity after selecting the records|
|Billing and Pricing|	5519210|	Error when creating price override of type "At transaction cost"|
|Project And Resource Management|	6089066|	"Open in Project" is visible in environments where customizations are present|
|Sales|	6002415|	Quote line cost amount is wrong when cost-QLD is in different currency|
|Subcontracting|	5556498|	"An item with the same key has already been added" error when actuals linked to Vendor Invoice are re-evaluated during Contract confirmation|
|Subcontracting|	6000962|	Subcontract field is not defaulted on vendor invoice lines based upon subcontract line|
|Time Entry|	6100760|	Time off entries do not appear on work hours calender when time entry of vacation or absence type is created on a working day|
### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=1093817&dbType=3&qc=0ba12b7b2693bd9dd120bcfb9ea3707a649f62040e948aeb93691bdad057c79a).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
