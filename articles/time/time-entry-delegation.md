---
title: Time Entry Delegation (preview)
description: This article explains how team members can give access to create, modify and submit time entries on their behalf to another resource in their organisation.
author: mohitmenon
ms.date: 09/19/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time Entry Delegation feature (Production Ready Preview)

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
1. This feature can be disabled at any time in the future and enabled at a later date once again.

After the feature is enabled, a new menu item named **Delegates (Production Ready Preview)** appears in the **My Work** section of the Project Operations and Team Member apps.

## Delegate Setup Experience

After enabling the Time Entry Delegation feature, navigate to the new **Delegates** menu item under **My Work.** Here, the default view is "My Delegates", which displays a list of resources that you assign as your delegates (initially empty).

To set another user as your delegate, follow these steps:
1. Select **New**. This action loads a form to fill in further details.
2. The first field to be populated is **Delegate**. You may select one of the bookable resources visible on this environment.
3. Next, **Start** date refers to the first day (this day included) from which you want to begin delegate access.
4. Finally, **End** date refers to the last day (this day included) of delegate access for the selected resource.
5. Select **Save** or **Save & Close**.
6. By completing these steps, this user is your **Delegate** and you are referred to as their **Delegator**.

The other two views available are: 
- **Assigned to Me**: List of users who have assigned you as their time entry delegate.
- **Inactive Delegates**: Resources that were previously visible under **My Delegates** but are explicitly deactivated now.

## Logging time as a delegate

To verify if you have been assigned as a delegate for another user: 
- Navigate to **Delegates** menu item.
- Switch the view to **Assigned to me**. The users visible in this list assigned you as their delegate, between Start and End dates on each record.

### Access rights provided to a time entry delegate

As a time entry delegate, a team member has access to:
- View all time entries within delegation Start and End dates for the delegator (original user).
- Create new time entries within delegation Start and End dates on behalf the delegator (original user).
- Modify all editable time entries within delegation Start and End dates on behalf the delegator (original user).
- Submit, Delete or Recall any time entries within delegation Start and End dates on behalf the delegator (original user).

### Time Entry experience for delegates

If you are assigned as a delegate for one or more resources in the current week, your time entry experience differs in the following manner:
- **Bookable Resource**: This field is now **mandatory** within the **New Time Entry** form and can be populated as either the logged-in user OR one of your delegators (original users) for this week.
- **Other time entry fields**: If one of the delegators (original users) was selected, options for fields like _Project, Project Task, Role_ are displayed corresponding to the delegator's projects, tasks and roles. The same behaviour is also replicated within the **Modern Time Entry Grid**, while trying to edit or populate time entry fields from the grid.

> [!NOTE]
> This change in behaviour for time entry fields within Quick Create form and Modern Grid only appear if a user is logging time **in a week where they have at least one delegator** assigned to them.
> If a user is logging time for a week where there are no delegators, time entry fields behave the same as they did before enabling delegation feature (default behaviour).


### Tracking time entries logged as a delegate

To simplify the tracking of time entries on behalf of other users (delegators), a new view "**My Time Entries as a Delegate"** is provided. This view contains time entries for all your delegators, in the current week _(subject to delegation Start and End dates)_.

## Keep track of time entries logged by a delegate

Similar to the previous section, a new view is provided for Delegators (original users) to track time entries logged by their delegates. This view is called **"Time entries by my delegates"**. The view contains:
- Time entries created by your delegates in the current week 
  

> [!NOTE]
> The 2 new views for time entries are visible to all time entry users, even without enabling the Time Entry Delegation feature, since views cannot be selectively filtered based on feature controls.

### Audit trail for delegated time entries

During this preview stage, delegated time entries can be primarily tracked using 2 fields:
- "Created by"
- "Modified by"

Time entry records can be tracked based on who created them and the last user to modify (edit or submit) them. These fields can provide a trail of records from creation to submission.

> [!NOTE]
> Enhanced tracking support for Delegation specific time entry fields (Delegator, Delegate Resource) will be provided in upcoming releases within the preview stage.

### Current limitations of the feature
- A user cannot assign more than one delegate within an overlapping date range. They can however, have more than delegate as long as their Start and End dates do not overlap.
- Time entries created by the original user (delegator) but modified by the delegate, do not appear within "Time entries logged by my delegates" view.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
