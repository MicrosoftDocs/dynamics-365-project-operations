---
title: What's new April 2021 - Project Operations lite deployment
description: This article provides information about the quality updates available in the April 2021 release of Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new April 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing._

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment version 4.9.0.221

## Features included in this release

The following features are included in this release:

- Non-stocked materials for projects. Key capabilities include:
  - Estimating and pricing non-stocked materials during the sales cycle for a project. For more information, see [Set up cost and sales rates for catalog products - lite](../pricing-costing/set-up-cost-sales-rates-catalog-products.md).
  - Tracking the use of non-stocked materials during project delivery. For more information, see [Record material usage on projects and project tasks](../../material/material-usage-log.md).
  - Invoicing used non-stocked material costs. For more information, see [Manage the billing backlog - lite](../proforma-invoicing/manage-billing-backlog-sales.md#product-billing-backlog).
  - New APIs in Dynamics 365 Dataverse allow create, update, and delete operations with **Scheduling entities**. For more information, see [Use Schedule APIs to perform operations with Scheduling entities](../../project-management/schedule-api-preview.md).

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2224568 | Added logic to enable customizations that involve invoking the invoice confirmation plug-in. |
| Billing and pricing | 2101098 | Improved the logic of default fields to proforma invoice: **Bill-to Address**, **Bill to Name**, and **Payment Terms** now default from the corresponding project contract customer record. |
| Billing and pricing | 2021413 | Updated the **Actual Cost** and **Sales** fields on the **Task** entity to include sales values from unbilled and billed expenses on tasks. |
| Billing and pricing | 2182110 | When copying a project contract, the contract line ID is regenerated in the destination project contract to ensure it's unique. |
| Opportunity Management | 2186741 | Added validations to ensure the **Origin** field and **Transaction Type** can't be updated on existing quote line details. |
| Opportunity Management | 2191353 | Milestones must not be created on a time and material contract line. |
| Opportunity Management | 2216956 | Fixed issues with **Update Prices**. |
| Planning and Tracking | 2182979 | Project copy function improved to ensure the expense estimate lines are copied from the original project. |
| Planning and Tracking | 2184144 | Project copy function improved to ensure the resource position name is copied from the original project. |
| Planning and Tracking | 2184799 | Project copy: Tightened control to ensure the estimated start date can't be changed while copying is in progress. |
| Planning and Tracking | 2185134 | Project copy: Destination project estimated start date is set to today's date. |
| Planning and Tracking | 2196373 | Project copy: Ensure the project manager and team member records aren't duplicated in the project team. |
| Planning and Tracking | 2211833 | Project copy: Resource assignments are copied from the source project task to the destination project. |
| Planning and Tracking | 2186541 | Fixed issues in the **Estimates** grid when grouping by resource. |
| Planning and Tracking | 2166906 | The transaction category from a task must be copied to the **Resource Assignment** entity. |
| Resource Management | 2125362 | Fixed issues with creating a generic team member using an hours-based allocation method. |
| Time and Expense | 2113603 | Fixed the customization-related issue with removing attributes from the **Time Entry** page. The system now checks if the attribute exists on the page before accessing them by using a script. |
| Time and Expense | 2204377 | Copied timesheets must show automatically when you select **Copy Week** during time entry. |
| Time and Expense | 2209059 | **Status** field can be edited for Dynamics 365 Field Service time entries. |
