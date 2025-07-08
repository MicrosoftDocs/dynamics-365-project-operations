---
title: What's new November 2021 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the November 2021 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new November 2021 - Project Operations Core deployment

_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.26.0.145, 4.26.0.148, 4.26.0.150, 4.26.0.155
  
## Features included in this release

The following features are included in this release:

- Project Scheduling application programming interfaces (APIs) now support the ability to create and delete Project buckets

## Quality updates

### Project Operations in Dataverse

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and Pricing | 2358236 | Invoice correction must allow corrections that have zero-price lines. |
| Resource Management | 2410072 | Allow setup of a resource that is assigned to the task as a project manager. |
| Billing and Pricing | 2430234 | Fix a cost performance calculation issue. |
| Time and Expense | 2436978 | Allow time to be entered in hh:mm format. |
| Billing and Pricing | 2448623 | Allow price lists to be updated after they are associated with an organizational unit. |
| Time and Expense | 2460396 | Allow a time entry to be deleted by clearing the cell. |
| Billing and Pricing | 2467386 | Allow a project that has a task to be deleted, even when the task is associated with a won quote. |
| Time and Expense | 2461744 | The **My failed approval** view contains only project approvals in the **Submitted** stage. |
| Time and Expense | 2464082 | Remove the link from project approvals to the approval set when a target status is matched. |
| Time and Expense | 2468108 | The Schedule job should not set a **Processing** status for the approval set. |
| Time and Expense | 2471503 | Delete approval sets that are seven days old. |
| Billing and Pricing | 2480687 | The quote line reference must not be removed when a quote line milestone is created. |
