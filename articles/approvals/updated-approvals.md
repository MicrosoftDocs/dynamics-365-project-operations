---
title: Navigate approvals (Preview)
description: Time-phased approvals in Project Operations let you manage time, expense, and material records from one form. Discover how to navigate the updated UI and tailor it to your team's needs.
author: abriccetti
ms.author: abriccetti
ms.date: 03/20/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Navigate approvals (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations updated the approvals experience in version 4.0.164.x. By turning on the **Time-phased approvals** feature in the feature control menu, you can host all relevant approvals views inside a form on the new *Approvals* entity (msdyn_projectapprovalheader). Each of the first six tabs in this form contains one type of approval record: time, material, expense, recall requests, absences/vacations, and nonproject approvals. Each tab has a number next to the tab name that indicates how many records of each type are pending approval by the current user. Each of these tabs contains two views, one for pending approvals and one to view past approvals. The admin tab contains the views for failed and processing approvals.

## Time-phased approvals

For time approvals, the UI uses a time-phased view similar to the time entry grid. It shows only one week's worth of approvals at a time, with a calendar selector to choose which week to show. The calendar selector has indicators that highlight which weeks have pending entries. By default, this view contains the following columns:

- Project
- Project Task
- NTE status
- Resource
- Billing type

The app groups all approval records that share the same data in these fields into a single row. The app sums the total submitted hours for each day of the week and provides a total for the entire week. Adding more columns to this view (or removing default columns) automatically updates the way rows are defined to use the newly added columns. When you select one of the totals, you see a view where each record comprising that total is an individual row. You can edit fields such as billing type, billable quantity, and external comments for each record.

## Customization

You can edit this new form by using the [maker portal](https://make.powerapps.com/). Go to the form named **ApprovalsForm** in the **Approvals** entity. Here, you can change each tab's views by selecting the subgrid in the tab and modifying the *Selected views* to include the views you want. You can also modify the default view, which is the view that appears each time the tab loads. However, the number shown next to the tab is calculated by using the default view assigned to that tab. If you change that default view, you affect that calculation and might lead to an incorrect number being shown. To modify the views for any of the tabs, go to the views for the *Project Approval* entity. Here, you can customize each view's columns or filters to your specifications.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
