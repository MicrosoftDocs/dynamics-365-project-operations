---
title: What's new May 2021 - Project Operations Core deployment
description: This article provides information about the quality updates available in the May 2021 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new May 2021 - Project Operations Core deployment

_Applies To: Project Operations Core_

This article applies to the following Dynamics 365 Project Operations components and versions:

   - Project Operations on Dataverse environment version 4.10.0.186.

## Features included in this release

The following features are included in this release:

- [Scheduling modes](../../project-management/scheduling-modes.md): Project managers can now define if a project should be managed using a fixed duration, fixed work, or fixed units scheduling mode.

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2224568 | Added logic to enable customizations that involve invoking the invoice confirmation plug-in. |
| Billing and pricing | 2101098 | Improved the logic of default fields to proforma invoice. These fields include, **Bill-to address**, **Bill to name**, and **Payment terms**. The fields now default from the corresponding project contract customer record. |
| Billing and pricing | 2021413 | Updated the **Actual cost** and **Sales** fields on the **Task** entity to include sales values from unbilled and billed expenses on tasks. |
| Billing and pricing | 2182110 | When copying a project contract, the contract line ID is regenerated in the destination project contract to ensure it's unique. |
| Opportunity Management | 2186741 | Added validations to ensure the **Origin** field and transaction type can't be updated on existing quote line details. |
| Opportunity Management | 2191353 | Milestone creation must not be allowed on a time and material contract line. |
| Opportunity Management | 2216956 | Fixed issues with **Update prices**. |
| Planning and Tracking | 2182979 | Project copy function improved to ensure that expense estimate lines are copied from the original project. |
| Planning and Tracking | 2184144 | Project copy function improved to ensure the resource position name is copied from the original project. |
| Planning and Tracking | 2184799 | Tightened the control when copying a project to ensure the estimated start date can't be changed while the copy is in progress. |
| Planning and Tracking | 2185134 | During the copy of a project, the destination project estimated start date is set to today's date. |
| Planning and Tracking | 2196373 | Ensure project manager and team member records are not duplicated in the project team when copying a project. |
| Planning and Tracking | 2211833 | Resource assignments are copied from the source project task to the destination project. |
| Planning and Tracking | 2186541 | Fixed issues in the **Estimates** grid when grouping by **Resource**. |
| Planning and Tracking | 2166906 | The transaction category from a task must be copied to the **Resource assignment** entity. |
| Resource Management | 2125362 | Fixed issues with creating a generic team member using the hours-based allocation method. |
| Time and Expense | 2113603 | Fixed customization-related issue with removing attributes from the **Time entry** page. The system checks if the attribute exists on the page before accessing the attribute by using a script. |
| Time and Expense | 2204377 | Copied timesheets must show automatically when you select **Copy Week**. |
| Time and Expense | 2209059 | The **Status** field is editable for Dynamics 365 Field Service time entries. |
