---
title: What's new May 2021 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the May 2021 release of Project Operations lite deployment.
author: sigitac
ms.date: 04/07/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new May 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This article applies to Project Operations components with version listed below.

| Project Operations on CDS environment |
| --- |
| 4.10.0.186 |

## Features included in this release

The following features are included in this release:

- [Scheduling modes](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/scheduling-modes) – project managers now have ability to define if project should be managed using fixed duration, fixed work or fixed units scheduling mode.

##

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and pricing | 2224568 | Added logic to enable customizations involving invoking invoice confirmation plugin. |
| Billing and pricing | 2101098 | Improved the logic of defaulting fields to proforma invoice: bill-to address, bill to name and Payment terms are now defaulted from corresponding Project contract customer record. |
| Billing and pricing | 2021413 | Updated the Actual cost and Sales fields on Task entity to include sales values from unbilled and billed expenses on tasks. |
| Billing and pricing | 2182110 | When copying a project contract the contract line ID is regenerated in the destination project contract to ensure it is unique. |
| Opportunity Management | 2186741 | Added validations to ensure Origin field and Transaction type cannot be updated on existing Quote line details. |
| Opportunity Management | 2191353 | Milestone creation must not be allowed on a &quot;Time and Material&quot; contract line. |
| Opportunity Management | 2216956 | Fixed issues with &quot;Update prices&quot; function. |
| Planning and Tracking | 2182979 | Project copy function improved to ensure Expense estimate lines are copied from original project |
| Planning and Tracking | 2184144 | Project copy function improved to ensure Resource position name is copied from original project |
| Planning and Tracking | 2184799 | Project copy: tightened control to ensure the estimated start date cannot be changed while copy is in progress |
| Planning and Tracking | 2185134 | Project copy: destination project estimated start date is set to today&#39;s date |
| Planning and Tracking | 2196373 | Project copy: ensure project manager and team member records are not duplicated in the project team. |
| Planning and Tracking | 2211833 | Project copy: resource assignments are copied from the source project task to the destination project |
| Planning and Tracking | 2186541 | Fixed issues in the Estimates grid when grouping by Resource. |
| Planning and Tracking | 2166906 | Transaction category from task must be copied to Resource assignment entity. |
| Resource Management | 2125362 | Fixed issues with creating a generic team member using hours - based allocation method |
| Time and Expense | 2113603 | Fixed customization related issue with removing attributes from time entry form. Now system will check if the attribute exists on the form before accessing them via script. |
| Time and Expense | 2204377 | Copied timesheets must show automatically when using &quot;Copy Week&quot; button on time entry control |
| Time and Expense | 2209059 | Status field is editable for Field Service time entries. |
