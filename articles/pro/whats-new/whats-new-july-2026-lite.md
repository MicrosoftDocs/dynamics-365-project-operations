---
title: What's new July 2026 - Project Operations Core
description: Learn about quality updates that are available in the July 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 07/27/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new July 2026 - Project Operations Core

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.169.3470.3.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Team Member Experience |**Track weekly and time-phased bookings within the Team Member app** <br><br> As a part of the Enhanced team member experience in Project Operations, team members can now also track their project bookings in a time-phased manner to know what they're staffed on currently and what's coming next.| [Track time-phased bookings](../../time/enhanced-team-member-experience.md#view-time-phased-project-bookings) |
| Time Entry |**Configure maximum hours that can be logged in a** <br><br> This feature is available as a part of a broader set of time entry behaviours that can now be configured on an environment. Admins can now configure the max. no. of hours of time entries that a user can log in a day (currently set to 24 hrs out of the box).| [Time Entry Configurations](../../time/time-entry-configurations.md) |
| Time Entry |**Configure time zone behaviour on the time entry grid** <br><br> This feature is available as a part of a broader set of time entry behaviours that can now be configured on an environment. Admins can now switch the time zone behaviour from time-zone aware (default, out of the box) to time-zone independent to prevent time zone related discrepancies for global teams.| [Time Entry Configurations](../../time/time-entry-configurations.md) |
| Resource Management |**Bulk Resource Reconciliation Experience (Preview)** <br><br> Resource Reconciliation within Projects was limited to a single resource, for a single time slice (day/week/month) and only applied to cases where a booking shortage existed. The Bulk Reconciliation feature now extends these capabilities to booking excesses as well, across multiple time slices (days/weeks/months). Resource Managers can now reconcile entire project teams, across the whole project range in one go by using the ""Reconcile All"" action.| [Bulk Resource Reconcile UI Experience](../../resource-management/resource-reconciliation-overview.md#resource-reconciliation-ui-for-projects) |
| Approvals |**Support for customizable first day of the week in the time-phased approvals view** <br><br> Now the calendar view for time approvals will support a custom first day of the week, and will not show Sunday as the first day| |
| Billing and Pricing |**Accounting date at Invoice level** <br><br> With this release, you can define the accounting date directly on the project invoice—independent of the transaction and document dates—giving your finance team control over the period in which billed revenue is recognized. When you specify an accounting date on the invoice, that date is applied to the billed sales actuals and flows through to the corresponding Finance & Operations transaction, so Project Operations and Finance & Operations stay aligned on a single, consistent posting date. This is especially valuable in integrated deployments where financial accuracy and audit compliance matter.| |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
