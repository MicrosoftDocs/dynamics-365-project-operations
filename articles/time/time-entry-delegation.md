---
title: Time Entry Delegation (preview)
description: This article explains how team members can give access to create, modify and submit time entries on their behalf to another resource in their organisation.
author: mohitmenon
ms.date: 09/19/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time Entry Delegation feature overview (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Time Entry Delegation allows users to give another resource temporary access to view, create, modify and submit time entries on their behalf. Team members can assign one delegate for limited time period and keep track of time entries created or submitted by their delegates.

This article provides an overview of the Time Entry Delegation feature, which is currently released as a **Production Ready Preview**. The article contains the following sections:

- Enable Time Entry Delegation (Production Ready Preview) feature
- Delegate setup experience
- Logging time as a delegate
- Keeping track of time entries logged by a delegate
- Current limitations of the feature

## Enable Time Entry Delegation (Preview) feature

To enable Time Entry Delegation, follow these steps.

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.145.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Delegation (Preview) feature**, and then select **OK**. If the text **Disable Time Entry Delegation (Preview)** is shown instead, it means the feature is already enabled.

After the feature is enabled, a new menu item named **Delegates (Production Ready Preview)** appears in the **My Work** section of the Project Operations and Team Member apps.

## Delegate Setup Experience

After enabling the Time Entry Delegation feature, navigate to the new **Delegates** menu item under **My Work.** Here, the default view is "My Delegates" which displays a list of resources who you have assigned as your delegates (initially empty).

To set another user as your delegate, follow these steps:
1. Select **New**. This action loads a form to fill in further details.
2. The first field to be populated is **Delegate**. You may select one of the bookable resources visible on this environment.
3. Next, **Start** date refers to the first day (this day included) from which you want to begin delegate access.
4. Finally, **End** date refers to the last day (this day included) of delegate access for the selected resource.
5. Select **Save** or **Save & Close**.

The other two views available are: 
- **Assigned to Me**: List of users who have assigned you as their time entry delegate.
- **Inactive Delegates**: Resources that were previously visible under **My Delegates** but have been explicitly deactivated now.

## Logging time as a delegate

To verify if you have been assigned as a delegate for another user: 
- Navigate to **Delegates** menu item.
- Switch the view to **Assigned to me**. The users visible in this list have assigned you as their delegate, between Start and End dates on each record.

### Access rights provided to a time entry delegate

As a time entry delegate, you have access to:
- View all time entries within the Start and End dates for the delegator (original user).
- Create new time entries within the Start and End dates on behalf the delegator (original user).
- Modify all editable time entries within the Start and End dates on behalf the delegator (original user).
- Submit, Delete or Recall any time entries within the Start and End dates on behalf the delegator (original user).

### Time Entry experience for delegates




