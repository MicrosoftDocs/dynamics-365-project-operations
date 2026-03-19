---
title: New Approvals UI
description: Navigating and customizing the updated approvals UI
author: abriccetti
ms.author: abriccetti
ms.date: 03/18/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Navigating Approvals

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The approvals experience Microsoft Dynamics 365 Project Operations has been updated as of version 4.0.164.x. By turning on the "Time-phased approvals" feature in the feature control menu. This hosts all relevant approvals views inside a form on the new *Approvals* entity (msdyn_projectapprovalheader). In this form each of the first 6 tabs contains one type of approval record: time, material, expense, recall requests, absences/vacations, and non-project approvals. Each tab has a number next to the tab name which indicates how many records of each type are pending approval by the current user. Each of these tabs contains two views, one for pending approvals and one to view past approvals. The admin tab contains the views for failed and processing approvals.

## Time-phased approvals

For time approvals, the UI has been updated to use a time-phased view similar to the time entry grid. Only one week's worth of approvals are shown at a time, with a calendar selector to choose which week should be shown. There are indicators on the calendar selector to highlight which weeks have pending entries. By default this view contains the following columns:

- Project
- Project Task
- NTE status
- Resource
- Billing type

All approval records which share the same data in these fields will be gouped together into a single row, with the total submitted hours summed for each day of the week as well as a total for the entire week. Adding additional columns to this view (or removing default columns) will automtaically update the way rows are defined to use the newly added columns. Selecting one of the totals will display a view where each record comprising that total is an individual row (similar to the old time approvals view) where fields such as biling type, billable quantity, and external comments can be edited for each record.

## Customization

This new form can be edited using the [maker portal](https://make.powerapps.com/) by going to the form named ApprovalsForm in the Approvals entity. Here each tab's views can be changed by selecting hte subgrid in the tab and modifying the *Selected views* to included the desired views. The default view (the view which is shown each time the tab is loaded) can also be modified, however, the number shown next to the tab is calculated using hte default view assigned to htat tab. Changing that default view will impact that calculation and potentially lead to an incorrect number being shown. To modify the views for any of the tabs go to the views for the *Project Approval* entity. Here each view's columns or filters can be customized to the users specifications.

