---
title: What's new July 2026 - Project Operations Integrated with ERP
description: Learn about the quality updates that are available in the July 2026  release of Microsoft Dynamics 365 Project Operations Integrated with ERP.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 07/27/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak

---

# What's new July 2026 - Project Operations Integrated with ERP

[!INCLUDE [banner](../includes/banner.md)]

**Applies To:**  Project Operations Integrated with ERP.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.169.3470.3.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.48.

## Project Operations dual-write map updates

The Project Operations July 2026 release doesn't include any changes to dual-write maps.

For the current list of Project Operations dual-write maps and versions, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Run the latest version of the map and enable all related table maps when you update your Project Operations Dataverse and Finance solutions. Some features might not work if you don't activate the latest map version. View the active map version in the **Version** column on the **dual-write** page. To activate a new version, select **Table map versions**, select the latest version, and save it. If you customized an out-of-box table map, reapply those changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If the map doesn't start, see the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Team Member Experience |**Track weekly and time-phased bookings within the Team Member app** <br><br> As a part of the Enhanced team member experience in Project Operations, team members can now also track their project bookings in a time-phased manner to know what they're staffed on currently and what's coming next.| [Track time-phased bookings](..//time/enhanced-team-member-experience.md#view-time-phased-project-bookings) |
| Time Entry |**Configure maximum hours that can be logged in a** <br><br> This feature is available as a part of a broader set of time entry behaviours that can now be configured on an environment. Admins can now configure the max. no. of hours of time entries that a user can log in a day (currently set to 24 hrs out of the box).| [Time Entry Configurations](../time/time-entry-configurations.md) |
| Time Entry |**Configure time zone behaviour on the time entry grid** <br><br> This feature is available as a part of a broader set of time entry behaviours that can now be configured on an environment. Admins can now switch the time zone behaviour from time-zone aware (default, out of the box) to time-zone independent to prevent time zone related discrepancies for global teams.| [Time Entry Configurations](../time/time-entry-configurations.md) |
| Resource Management |**Bulk Resource Reconciliation Experience (Preview)** <br><br> Resource Reconciliation within Projects was limited to a single resource, for a single time slice (day/week/month) and only applied to cases where a booking shortage existed. The Bulk Reconciliation feature now extends these capabilities to booking excesses as well, across multiple time slices (days/weeks/months). Resource Managers can now reconcile entire project teams, across the whole project range in one go by using the ""Reconcile All"" action.| [Bulk Resource Reconcile UI Experience](../resource-management/resource-reconciliation-overview.md#resource-reconciliation-ui-for-projects) |
| Approvals |**Support for customizable first day of the week in the time-phased approvals view** <br><br> Now the calendar view for time approvals will support a custom first day of the week, and will not show Sunday as the first day| |
| Project Financials |**Enable project resources on general journal entries** <br><br> Enhancements were made to specify the bookable resource on the general journal. This feature enables you to post general journals at the aggregate level without a resource, or in the context of a specific bookable resource.| |
| Project Financials |**Post project invoice proposals using multithreaded batch tasks** <br><br> Enhancements were made to specify the bookable resource on the general journal. This feature enables you to post general journals at the aggregate level without a resource, or in the context of a specific bookable resource.| |
| Billing and Pricing |**Accounting date at Invoice level** <br><br> With this release, you can define the accounting date directly on the project invoice—independent of the transaction and document dates—giving your finance team control over the period in which billed revenue is recognized. When you specify an accounting date on the invoice, that date is applied to the billed sales actuals and flows through to the corresponding Finance & Operations transaction, so Project Operations and Finance & Operations stay aligned on a single, consistent posting date. This is especially valuable in integrated deployments where financial accuracy and audit compliance matter.| |
