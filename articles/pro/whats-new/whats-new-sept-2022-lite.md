---
title: What's new September 2022 - Project Operations lite deployment
description: This article provides information about the quality updates that are available in the September 2022 release of Microsoft Dynamics 365 Project Operations lite deployment.
author: ramagadu
ms.date: 09/28/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new September 2022 - Project Operations lite deployment

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.46.0.60
  
## Features included in this release

|Feature area|Feature name|More information|
| --- | --- | --- |
|Opportunity Management|**Revision and Activation of Quotes** </br> </br>  Microsoft Dynamics 365 Project Operations brings in the full support of the Sales process. Project quotes can be activated to represent a state where the quote is read-only and is being reviewed. Activated quotes can be revised to created new quotes with an incremented revision number. Activated project quotes or quote revisions can be closed as won or lost.|[Activate and revise a project quote](/dynamics365/project-operations/sales/activation-and-revision)|
|Billing and Pricing|**Time-zone agnostic price defaulting** </br> </br> Project Operations has introduced the concept of a time-zone agnostic date on all project actuals. This new field called, **Transaction date**, is now available on journal lines and actuals, and will be used to the store the date on which the transaction occurred (without converting it to UTC). This date will be used for downstream processes like price defaulting and invoice creation. |[Determine cost rates for project-based estimates and actuals](/dynamics365/project-operations/pro/pricing-costing/cost-price-resolution-sales) </br> </br> [Determine sales prices for project-based estimates and actuals](/dynamics365/project-operations/pro/pricing-costing/sales-price-resolution-sales)|
|Billing and Pricing|**Date-effective price overrides in Project Operations** </br> </br> Date-effective price overrides provide a way to override or change specific prices in the price list.|[Date-effective price overrides](/dynamics365/project-operations/pricing-costing/dateffective_price_overrides)|
|Time and Expense|**Global Approver** </br> </br> Allows ISV and centralized approval regardless of Project or Team member status within the Project|[Security and approvals](/dynamics365/project-operations/approvals/approvals-security)|

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|2754422|Material and Expense estimates are not flowing to  Microsoft Dynamics 365 Finance upon copying projects in Dataverse.|
|Time and Expense|2787409|Able to approve non-project time entry as invalid approver.|
|Opportunity Management|2788907|Updated error message on uniqueness validation for order lines include flags.|
|Time and Expense|2842253|Null exception handling for time approval.|
|Billing and Pricing|2844181|Failure in getting correlation id blocking invoice creation.|
|Billing and Pricing|2876628|QLD, CLD - Estimate price list resolution should use legacy date range fields of the price list.|
|Subcontracting|2893222|When a subcontract line does not have a role specified, it should be possible to select it on a Team member for any role.|
