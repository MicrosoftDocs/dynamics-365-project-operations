---
title: What's new September 2022 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the September 2022 release of Microsoft Dynamics 365 Project Operations Core deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new September 2022 - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.46.0.60

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
| Opportunity Management | **Revision and Activation of Quotes**<br>Project Operations brings in the full support of the sales process. Project quotes can be activated to represent a state where the quote is read-only and is being reviewed. Activated quotes can be revised to create new quotes that have an incremented revision number. Activated project quotes or quote revisions can be closed as won or lost. | [Activate and revise a project quote](/dynamics365/project-operations/sales/activation-and-revision) |
| Billing and Pricing | **Time-zone agnostic price defaulting**<br>Project Operations has introduced the concept of a time-zone agnostic date on all project actuals. A new field, **Transaction date**, is now available on journal lines and actuals, and will be used to store the date when the transaction occurred, but without converting that date to Coordinated Universal Time. This date will be used for downstream processes such as price defaulting and invoice creation. | <p>[Determine cost rates for project-based estimates and actuals](/dynamics365/project-operations/pro/pricing-costing/cost-price-resolution-sales)</p><p>[Determine sales prices for project-based estimates and actuals](/dynamics365/project-operations/pro/pricing-costing/sales-price-resolution-sales)</p> |
| Billing and Pricing | **Date-effective price overrides in Project Operations**<br>Date-effective price overrides provide a way to override or change specific prices in the price list. | [Date-effective price overrides](/dynamics365/project-operations/pricing-costing/dateffective_price_overrides) |
| Time and Expense | **Global Approver**<br>This feature enables independent software vendor (ISV) and centralized approval, regardless of the project or team member status in the project. | [Security and approvals](/dynamics365/project-operations/approvals/approvals-security) |
|Project Planning and Tracking|**Use Project schedule APIs to perform operations with Scheduling entities** </br> </br>The resource assignment contour editing API lets developers programmatically specify a task assignee's effort across any supported date range for more granular time phased effort planning.|[Use Project schedule APIs to perform operations with Scheduling entities](/dynamics365/project-operations/project-management/schedule-api-preview)|

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2754422 | Material and Expense estimates don't flow to Dynamics 365 Finance when projects are copied in Dataverse. |
| Time and Expense | 2787409 | A non-valid approver can approve a non-project time entry. |
| Opportunity Management | 2788907 | Updated error message on uniqueness validation for order lines that include flags. |
| Time and Expense | 2842253 | Null exception handling for time approval. |
| Billing and Pricing | 2844181 | Failure to get the correlation ID blocks invoice creation. |
| Billing and Pricing | 2876628 | QLD, CLD - Estimate price list resolution should use legacy date range fields of the price list. |
| Subcontracting | 2893222 | If no role is specified for a subcontract line, it should be possible to select that line on a team member for any role. |
