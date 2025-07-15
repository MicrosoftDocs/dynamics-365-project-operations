---
title: What's new December 2021 - Project Operations Core
description: This article provides information about the quality updates that are available in the December 2021 release of Project Operations Core.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new December 2021 - Project Operations Core

_Applies To: Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.27.0.195, 4.27.0.242, 4.27.0.244


## Features included in this release

### Subcontract management 

- [Subcontracting project team  members](../subcontracting/subcontracting-project-team-members.md): A project manager can create named or generic team members with subcontracts and subcontract lines to impact staffing and estimation.
- [Subcontracting options for project team members](../subcontracting/subcon-options.md): When making staffing choices for named or generic project team members, the project manager can review existing subcontracts or create new subcontracts for one or more project team members. 
- [Cost estimation of subcontracted resource assignments](../subcontracting/costing-subcon-ra.md): Project cost estimation will take into account subcontracted resource assignments and will cost them using the purchase price lists associated with subcontracts. 
- [Configure Schedule Board to show contract workers and subcontracted capacity](../subcontracting/configure-sb-subcon.md): Schedule board in Project Operations can now be configured to search for and suggest contract worker type of bookable resources and subcontracted capacity along with employees. This configuration can be applied when searching for resources within the context of staffing for a specific project requirement or when searching outside of the context of a project requirement.
- [Staffing a project with contract workers and subcontracted capacity](../subcontracting/staffing-cw.md): Contract workers can now be booked on projects leveraging schedule board experiences.
- [Recording time, expenses, and material usage on projects for subcontracted components](../subcontracting/recording-subcon-actuals.md): Contract workers can record time and expenses, and project team members can also record usage of materials purchased using a subcontract on a project. This will result in recording accurate costs on projects that use purchased capacity or materials.
- [State transitions on a subcontract](../subcontracting/subcon-states.md): Subcontracts can be confirmed to complete negotiation with the vendor, closed to indicate completion of delivery, or canceled to indicate termination of contract with the vendor before completion of delivery.

### Task Planning
- Improved troubleshooting for system administrators. When a user can't open a project, the administrator can review non-license related errors generated from Project for the web in [Project scheduling logs](../../project-management/schedule-api-logs.md).
- [Use task checklists in Microsoft Project for the web](https://support.microsoft.com/en-us/office/use-task-checklists-in-microsoft-project-for-the-web-c69bcf73-5c75-4ad3-9893-6d6f92360e9c). In Microsoft Project for the web, you can add a checklist to a task to keep track of specific items.

## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Planning and Tracking | 2392596 | Schedule APIs now allow updates to the **Effort remaining**, **Effort completed**, and **% Complete** fields. |
| Planning and Tracking | 2478497 | Schedule APIs **Activity number** and **Task ID** fields can be blank on input because the system will populate them using automated numbering.|
| Time and Expense | 2468135 | The number of approval retries is reduced from five to three. |
| Time and Expense | 2468188 | Fixed the issue with log text exceeding the maximum length in the **notetext** attribute of the **annotation** entity. |
