---
title: Approvals overview
description: This article provides information about working with approvals in Project Operations.
author: suvaidya
ms.date: 12/09/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti

---

# Approvals overview

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Time, expense, and material usage submissions move through an approval workflow. After the entries are approved, transactions are recorded in actuals or time is booked in the schedule.

## Approvals workflow

When you create and submit a time, expense, or material usage entry, you also create an approval record. The project approver or manager reviews and approves the entry. If the entry is related to a project, the actuals are created when you approve it. This process lets you track the cost and billing. You can find these records in the *Approvals* view under the *Projects* area of the sitemap. Here, you can see different views for the different types of approvals and past approvals.

> [!NOTE]
> For time approvals, a time phased grid is available where you can view one week's worth of time approvals (past or pending) at a time, summarized similar to the time entry grid. To use this view, enable the "Time Phased Approvals" feature from the feature control menu and select *Calendar view for time approvals* from the view selector.

## Approve an entry

The **Approvals** page allows you to switch between different views so that you can view the different types of approvals.
  
1. Go to the **Approvals** page and select **Expenses**, **Time**, **Material Usage**, or **Recalls**.
1. Review each approval, and select the ones you want to approve.
1. Select **Approve** to approve the selected entries.
The system processes these entries and creates actuals.

> [!NOTE]
> Approval actions (approve, reject, cancel) must be completed by selecting the appropriate action button on the ribbon, or by using the [process project approval sets API](dev-programmatic-approvals.md). You can't complete them by directly updating the Record Stage on the Project Approval record.

## Reject an entry

As the project approver, you might need to send an entry back to a user for correction.
  
1. Go to the **Approvals** page and select the entry to reject.
1. Select **Reject**.
1. Optional, add a comment in the **Rejection Comments** dialog box to inform the user why the entry is being rejected.
1. Select **OK**. The entry is returned to the user.
  
## Cancel approval

In some cases, you might need to cancel a previously approved entry. When you cancel an approval, you negate any actuals that you created when you originally approved the entry. Due to this action, canceling a previously approved entry has a financial impact.

## Approve recall requests

In some cases, a consultant might need to recall a previously approved entry. Approving a recall request is like canceling a previously approved entry. The project approver must approve the recall to reverse the transaction in actuals.

> [!NOTE]
> Depending on the view, some actions (approve, reject, or cancel) might not appear on the ribbon.

## Specify Project approvers

Each project has a number of project team members. You can specify which team members are also Project approvers.

1. Go to the **Projects** page and open the project from the list.
1. On the **Team** tab, select the team member who is a Project approver and then select **Edit**.
1. Set the **Project Approver** field to **Yes**.
1. Select **Save**.
1. Repeat steps 2-4 to add more Project approvers.

## Configure the user's manager

1. Go to **Settings** > **Security** > **Users**.
1. Select the user to whom you want to assign a manager. In the **Organization Information** area, select the manager from the list.
1. Select **Save**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
