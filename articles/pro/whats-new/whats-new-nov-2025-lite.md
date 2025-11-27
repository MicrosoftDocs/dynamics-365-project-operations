---
title: What's new November 2025 - Project Operations Core
description: Learn about quality updates that are available in the November release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 11/27/2025
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new November 2025 - Project Operations Core

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.161.0.36.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Invoicing |**Billing Hub Phase 3** <br><br> The latest updates on Billing Hub address customer feedback for better visibility and control, reduces manual effort, and aligns with the long-term goal of making Billing Hub the central invoicing workspace. <br> The updates can be accessed by enabling the flag 'Enable Billing Hub updates'. Key enhancements include: Visibility for 'Not Ready to Invoice' transactions, Streamlined Invoice Creation, Instant Amount Calculations & Notifications, Performance & UX Enhancements | |
| Approvals |**New Time Phased Approvals View** <br><br> The approvals view for time transactions is getting an overhaul to show information in a clearer and more concise format. Time approvals are shown one week at a time, with transactions grouped together based on the columns added to the view in one row. Project Managers can then open a cell in that row to see more details for each day's entries and make edits as necessary.| |
| Project Management |**Customize Task Pane** <br><br> With this new feature enabled, clicking the "i" icon opens a customizable task pane that lets you manage tasks, customize them, and trigger business flows directly from the task grid context. You can still access the standard Project task pane via the overflow menu, giving you complete flexibility to choose between the custom Dataverse task pane and the Office task pane based on your requirements.| |
| Project Management |**Copy project new experience** <br><br> The new copy experience allows Project Managers to copy projects by setting configurations like Project name, Calendar template, Schedule mode, Contracting unit, Currency, etc. The flow can also be customised as per your needs and copy projects to new or existing projects with no Work Breakdown Structure.| |
| Project Management |**Copy externally scheduled projects** <br><br> The new copy experience brings along the copy project capability for an externally scheduled project. Now project managers can easily copy projects to new and existing projects with no WBS. This brings feature parity for externally scheduled projects.| |


## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference no.** | **Quality update** |
| --- | --- | --- |
|Time Entry|	4583099|	Import From Resource Assignments is importing for incorrect days|
|Billing and Pricing|	5070121|	Unexpected error while updating applied advance amount an a confirmed invoice line |
|Project Planning|	5188687|	Start and Finish Date fields appear on forms even after being marked as hidden from maker portal|
|Subcontracting|	5344230|	Price Mismatch on Vendor Invoice Line Reconciliation|
|Subcontracting|	5346558|	Material estimate (line) doesn't copy the project task from the material estimate (line) onto the subcontract line that is created using subcontracting options|
|Subcontracting|	5361570|	Defaulting for Unit and Unit Group is not working correctly for Subcontract Line|
|Time Entry|	5389918|	Vendor Field isn't defaulted in Actual with subcontract and subcontract line|
|Subcontracting|	5534458|	Tax on the vendor invoice lines is incorrectly to unbilled sales actuals|
|Billing and Pricing|	5744336|	Preventing deletion of contract lines that have unbilled actuals|
|Subcontracting|	5769534|	Continue Booking button is disabled when all resources are shortlisted from Resource Recommendations|
|Project Planning|	5770199|	% Complete doesn't align with the EAC |
|Project And Resource Management|	5820499|	Resource assignment currency should match project currency to display estimates correctly|
|Project Budgeting And Forecasting|	5822655|	Month rollover issue during default project budget period creation|

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
