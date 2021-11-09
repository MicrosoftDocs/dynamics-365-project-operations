---
title: What's new November 2021 - Project Operations lite deployment
description: This topic provides information about the quality updates available in the November 2021 release of Project Operations lite deployment.
author: sigitac
ms.date: 11/09/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# What's new November 2021 - Project Operations lite deployment

_Applies To: Lite deployment - deal to proforma invoicing_

This topic applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Microsoft Dataverse environment version 4.26.0.145
  
## Features included in this release

The following features are included in this release:

- Project Scheduling APIs now support the ability to create and delete Project buckets

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing and Pricing | 2358236 | Invoice correction must allow corrections with zero price lines. |
| Resource Management | 2410072 | Allow set up of a resource that's assigned to the task as a Project manager. |
| Billing and Pricing | 2430234 | Fix cost performance calculation issue. |
| Time and Expense | 2436978 | Allow time to be entered in a hh:mm format. |
| Billing and Pricing | 2448623 | Allow price lists to be updated after they are associated with an organizational unit. |
| Time and Expense | 2460396 | Allow a time entry to be deleted by clearing the cell. |
| Billing and Pricing | 2467386 | Allow a project with task to be deleted even when the task is associated with a won quote. |
| Time and Expense | 2461744 | **My failed approval** view only contains project approvals in the **Submitted** stage. |
| Time and Expense | 2464082 | Remove the link from project approvals to the approval set when matching a target status. |
| Time and Expense | 2468108 | The Schedule job should not set a **Processing** approval set status. |
| Time and Expense | 2471503 | Delete approval sets that are seven days old. |
| Billing and Pricing | 2480687 | The quote line reference must not be removed when creating a quote line milestone. |
