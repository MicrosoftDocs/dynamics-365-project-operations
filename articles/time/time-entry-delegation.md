---
title: Time Entry Delegation (preview)
description: This article explains how team members can give access to create, modify, and submit time entries on their behalf to another resource in their organisation.
author: mohitmenon
ms.date: 09/23/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time entry delegation feature (production ready preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Time entry delegation lets a resource temporarily view, create, modify, and submit time entries for another user. Team members assign one delegate for a limited period and track time entries the delegate creates or submits.

This article gives an overview of time entry delegation, a **Production Ready Preview** feature. It includes:

- Enable the time entry delegation (production ready preview) feature
- Set up a delegate
- Log time as a delegate
- Track time entries logged by a delegate
- Limitations

## Enable time entry delegation (preview) feature

To enable Time Entry Delegation, follow these steps.

1. Update your Microsoft Dynamics 365 Project Operations environment to version **4.145.0.X or later**. Earlier versions don't include this feature.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, go to **Settings** > **General**, and select **Parameters**.
1. When the list of organization units appears, select the **Organization Units** row in a column that isn't a link.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Delegation (Preview) feature**, and then select **OK**. If you see **Disable Time Entry Delegation (Preview)**, the feature is already enabled.
1. You can disable and re-enable the feature at any time.

After you enable the feature, the **Delegates (Production Ready Preview)** menu item appears in the **My Work** section of the Project Operations and Team Member apps.

## Delegate setup experience

After you enable the time entry delegation feature, go to **My Work.** > **Delegates**. The default view (My Delegates) shows the resources you've assigned as delegates. The list is empty at first.

Set another user as your delegate:
1. Select **New** to open the form.
1. Fill the **Delegate** field. You can select any bookable resource in this environment.
1. Enter the **Start** date. It's the first (inclusive) day of delegate access.
1. Enter the **End** date. It's the last (inclusive) day of delegate access.
1. Select **Save** or **Save & Close**.
1. After you save, the user becomes your **Delegate** and you're their **Delegator**.

Other available views:
- **Assigned to Me**: Shows users who assigned you as their time entry delegate.
- **Inactive Delegates**: Shows resources previously under **My Delegates** that are now deactivated.

## Log time as a delegate

Check if you're assigned as a delegate for another user:
- Go to the **Delegates** menu.
- Switch the view to **Assigned to me**. Users in this list assigned you as their delegate between the Start and End dates on each record.

### Access rights provided to a time entry delegate

As a time entry delegate, you can:
- View all time entries between the delegation Start and End dates for the delegator (original user).
- Create new time entries between the delegation Start and End dates on behalf of the delegator (original user).
- Change any editable time entries between the delegation Start and End dates on behalf of the delegator (original user).
- Submit, delete, or recall any time entries between the delegation Start and End dates on behalf of the delegator (original user).

### Time entry experience for delegates

If you're a delegate for one or more resources this week, your time entry experience changes in these ways:
- **Bookable Resource**: This field is now required in the **New Time Entry** form and you can select either yourself or one of your delegators (original users) for this week.
- **Other time entry fields**: When you select a delegator (original user), options for fields like Project, Project Task, and Role appear based on the delegator's projects, tasks, and roles. The same behavior appears in the **Modern Time Entry Grid** when you edit or enter time entry fields in the grid.

> [!NOTE]
> This change in behavior for time entry fields in the Quick Create form and Modern Grid appears only in a week when you have at least one delegator.
> If you log time in a week with no delegators, the fields behave as they did before you enable the delegation feature (default behavior).


### Tracking time entries logged as a delegate

To simplify tracking time you enter for delegators, use the **My Time Entries as a Delegate** view. It shows time entries for all your delegators in the current week (subject to the delegation Start and End dates).

## Keep track of time entries logged by a delegate

The **"Time entries by my delegates"** view lets delegators (original users) track time entries their delegates log. It contains:
- Time entries your delegates created in the current week
  

> [!NOTE]
> All time entry users see the two new views, even if the Time Entry Delegation feature isn't enabled, because view availability can't be filtered by feature controls.

### Audit trail for delegated time entries

During preview, track delegated time entries with two fields:
- **Created by**
- **Modified by**

Use these fields to see who created a time entry and who last modified (edited or submitted) it. They provide an audit trail from creation to submission.

> [!NOTE]
> Upcoming preview releases add enhanced tracking for the **Delegator** and **Delegate Resource** fields.

### Current limitations of the feature
- A user can't assign more than one delegate for overlapping date ranges. A user can have multiple delegates as long as their **Start** and **End** dates don't overlap.
- Time entries the original user (delegator) created but a delegate modified don't appear in the **"Time entries by my delegates"** view.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
