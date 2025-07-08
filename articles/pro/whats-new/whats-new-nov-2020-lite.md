---
title: What's new November 2020 - Project Operations Core deployment - deal to proforma invoicing
description: This article provides information about the quality updates available in the November 2020 release of Project Operations Core deployment - deal to proforma invoicing. 
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new November 2020 - Project Operations Core deployment - deal to proforma invoicing

_**Applies To:** Core deployment - deal to proforma invoicing_

The following table lists the updates to Project Operations on CDS environment version 4.4.0.70.

| Feature area                 | Reference number | Quality update                                                                                                                                                                    |
|------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Opportunity management       | 2036993          | Estimate line and resource   assignment contract lines are updated on winning quotes when the quote line   type is **All tasks**.                                                 |
| Opportunity management       | 2071514          | Can't create an invoice for a   fixed price milestone on a contract that has task-based billing enabled.                                                                          |
| Billing and pricing          | 2070392          | Project contract lines on the   invoice increase every time **Refresh invoice transactions** is   selected.                                                                       |
| Project planning             | 2043336          | Unable to delete a project team member record.                                                                                                                                    |
| Project planning             | 2046013          | Inconsistent behavior for   Estimates tag columns during load vs. on change of time-phase type.                                                                                   |
| Project planning             | 2046647          | Start and end times are off by   an hour when resource requirements are generated from project team members.                                                                      |
| Project planning             | 2053879          | (Per the upcoming CDS   rollout)   PublishUnassignedAssignments   breaks an attempt to save a task when  the error, "The   value passed for ConditionOperator.In is   empty." |
| Project planning             | 2055501          | Leaving the **Project Start   Date** empty causes a failure in the schedule.                                                                                                      |
| Project planning             | 2066817          | Can't create a generic   resource   using the people picker on   the **Tasks** tab.                                                                                               |
| Project planning             | 2067034          | **View Details** button isn't available on the **Details of Task** page.                                                                                                         |
| Resource management          | 2046667          | Generic team members aren't   deleted even after all resources are fulfilled.                                                                                                     |
| Time and quick expense entry | 2047499          | The **New** button on the Time   Entry page opens the **New Email Signature** page.                                                                                               |
| Time and quick expense entry | 2059859          | Unexpected   pop-up opens when creating an expense entry.                                                                                                                         |
| Other                        | 2044181          | [PO Uninstallation] - The error,   "Record is unavailable" occurs when you try to uninstall   **msdyn_ProjectServiceCore_Patch** and msdyn Project service core solutions.        |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
