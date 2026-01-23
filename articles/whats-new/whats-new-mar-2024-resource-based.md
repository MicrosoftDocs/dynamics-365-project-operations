---
title: What's new March 2024 - Project Operations Integrated with ERP
description: This article provides information about the quality updates that are available in the March 2024 release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: tulsijhaveri
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.update-cycle: 1095-days
ms.topic: whats-new
ms.reviewer: 
ms.author: dishantpopli
---

# What's new March 2024 - Project Operations Integrated with ERP

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.92.0.2.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.39.

## Project Operations dual-write maps updates

The following table shows the Dual-write maps that are modified or added in the Project Operations March 2024 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.18 | Latest version updated |
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.7 | Latest version updated |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Management | **Removal of team member limits for externally scheduled projects**<br><br>For externally scheduled projects, we no longer impose the limit of 300 resources assigned per project. This limit was due to the dependency on Project for the web. | [External scheduling](../project-management/external-scheduling.md) |
| Project Estimates | **Project estimate updates**<br><br>This feature enhancement simplifies the creation and editing of both **expense** and **material** estimates for a project. Previously, the materials and expense estimates tabs were separate, now they're consolidated into a new **Estimates**. Additionally, the previously labeled **Estimates** tab is updated to **Time phased estimates** with no other changes. The enhanced experience allows users to easily add new expense and material estimates using a quick create form, with the convenience of in-line editing directly on the grid. Within the grid of the new **Estimates** tab, two views are provided: **Expense** and **Materials**. Each grid displays the **Cost** line (parent) and **Sales** line (child). | [Financial estimates for expenses on projects](../project-management/create-expense-estimates.md) |
| Project Financials | **Enable default financial dimensions for bookable resources.**<br><br> **Use employment default dimensions on integration journals** is a new feature that is available in feature management. When enabled and the **Dynamics 365 HR Integration to URS app** is installed, employee financial dimensions are considered for some transactions. | [Financial dimension defaults](../project-accounting/financial-dimension-defaults.md) |
| Sales | **Sales copy with company**<br><br>This feature introduces the capability to **select an alternate company** when **copying Opportunity, Quote, and Project Contract records**. With this feature, users gain flexibility to seamlessly duplicate relevant records across different companies. This flexibility streamlines efficient templatization and repathing of opportunities, quotes, and contracts. | [Copy-project-based-quotes](../sales/copy-project-based-quotes.md)<br><br>[Copy project-based contracts](../sales/copy-project-based-contracts-sales.md)<br><br>[Copy project opportunities](../sales/copy-project-based-opportunity.md) |
| Project Management | **Copilot for project**<br><br>**Copilot for project** streamlines project management tasks the system in plain English. With an input of the project name and description, **Copilot generates a preliminary work breakdown structure**, simplifying the task planning process. For ongoing projects, Copilot for project facilitates **risk assessment by analyzing the risk register and providing suggested mitigations along with probabilities of occurrence** for each risk identified. Moreover, project managers can effortlessly **generate detailed status reports through Copilot, integrating concise summaries of scheduling and financial data while also delivering insightful content on overall project progress, financial performance, and schedule adherence.** Additionally, Copilot offers a Sidecar chat feature, **allowing users to initiate these actions through typed command**, enhancing accessibility and efficiency in project management. | [Project management Copilot overview](../project-management/copilot-features.md) |
| Performa invoicing | **Improved project invoicing usability and performance**<br><br>The **Billing hub experience** aims to provide a rich, consolidated view of contracts, contract lines, related actuals, and key invoicing insights **prior to invoice creation** to help accountants and billing users create proforma invoices quickly and efficiently. Using the platform's out-of-the-box nested grid functionality, you can complete invoice creation from a single unified view, eliminating the need to navigate between forms or views to validate data, thus leading to faster processing of invoices. |     |
| Project Procurement | **Advance subcontracting**<br><br>This feature lets users generate subcontracts, document timesheets, expenses, and other relevant information that subcontractors provide in Dataverse. For every subcontract in Dataverse, the system automatically generates purchase orders in Finance. Likewise, for every recorded timesheet or expense in Dataverse, the system generates corresponding product receipts in Finance. When a subcontractor submits an invoice in Finance, the Accounts payable (AP) clerk gains access to all recorded timesheets and expenses that are associated with the subcontract. The AP clerk can then perform a three-way matching process and book the invoice in Finance. | [Subcontract purchase orders overview](../pro/subcontracting/subconpurchaseorders.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |
| Billing and Pricing | 3564025 | Invoice field and basis quantity aren't set when manually creating an ILD. |
| Project Planning and Tracking | 3651668 | When you delete a team member from Dataverse, async delete fails if PSS doesn't know the team member. This shouldn't be the case. |
| Project Planning and Tracking | 3660615 | Misleading error message for copy project. |
| Time Entry | 3776471 | \[Modern Grid\] Possibility of creating invalid time entries through in-grid editability. |
| Project Budgeting | 3779420 | Material Budget Line shouldn't have both WriteIn and Existing product. |
| Billing and Pricing | 3780647 | Invoice Date changes to next day when UTC date changes to next day. |
| Billing and Pricing | 3781951 | CopyProductPricesFromPriceList doesn't filter on active state. |
| Subcontracting | 3786516 | Dataflow mapping issue for resource category. |
| Project Budgeting | 3792450 | Add logic to Fetch Price List from Contract associated to Project. |
| Project Budgeting | 3793826 | Actual to Budget Line Unit Price Should Consider Unit Conversion Factor. |
| Project Budgeting | 3802808 | During budget evaluation, don't match fixed price project contract sales actual to any budget line. |
| Billing and Pricing | 3804223 | \[CostPlusPricing\] : Price defaulting errors anytime an override is created for a role price that is AtCost or Markup. |
| Billing and Pricing | 3805992 | You shouldn't be able to create AtCost or markup based category price from nonsales price lists. |
| Billing and Pricing | 3815475 | Able to create/update estimate lines with invalid subcontract lines. |
| Project Planning and Tracking | 3815578 | Extend booking always rounds minutes down resulting in less a minute unbooked. |
| Billing and Pricing | 3834839 | Post Project Parameter Create creates org unit without regard to field and doesn't set currency. |
| Billing and Pricing | 3840851 | Recalculate Totals Button Show For All SalesOrder Views. |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?bugId=886261).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
