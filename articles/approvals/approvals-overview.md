---
title: Approvals overview
description: This article provides information about working with approvals in Project Operations.
author: suvaidya
ms.date: 08/21/2025
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
When you create and submit a time, expense, or material usage entry, an approval record is created. The project approver or manager reviews and approves the entry. If the entry is related to a project, the actuals will be created when it's approved. This allows the cost and billing to be tracked.

## Approve an entry
The **Approvals** page allows you to switch between different views so that you can view the different types of approvals.
  
1. Go to the **Approvals** page and select **Expenses**, **Time**, **Material Usage**, or **Recalls**.
2. Review each approval, and select the ones you want to approve.
3. Select **Approve** to approve the selected entries.
The system processes these entries and creates actuals.

> [!NOTE]
> Approval actions (approve, reject, cancel) must be completed by selecting the appropriate action button on the ribbon, or by using the [process project approval sets API](dev-programatic-approvals.md). You can't complete them by directly updating the Record Stage on the Project Approval record.

## Reject an entry
As the Project approver, you may have to send an entry back to a user for correction.
  
1. Go to the **Approvals** page and select the entry to reject. 
2. Select **Reject**.
3. Optional, add a comment in the **Rejection Comments** dialog box to inform the user why the entry is being rejected.
4. Select **OK**. The entry will be returned to the user.
  
## Cancel approval
In some cases, you might need to cancel a previously approved entry. When an approval is canceled, any Actuals that were created when it was originally approved are negated. Due to this, canceling a previously approved entry has a financial impact. 

## Approving recall requests
In some cases, a consultant may need to recall a previously approved entry. Approving a recall request is like canceling a previously approved entry. The project approver is required to approve the recall to reverse the transaction in Actuals.

> [!NOTE]
> Depending on the view, some actions (approve, reject, or cancel) may not appear on the ribbon.

## Specify Project approvers
Each project has a number of project team members. You can specify which team members are also Project approvers.

1. Go to the **Projects** page and open the project from the list.
2. On the **Team** tab, select the team member who will be a Project approver and then select **Edit**.
3. Set the **Project Approver** field to **Yes**.
4. Select **Save**.
5. Repeat steps 2-4 to add more Project approvers.

## Configure the user's manager

1. Go to **Settings** > **Security** > **Users**.
2. Select the user to whom you are assigning a manager and in the **Organization Information** area, select the manager from the list. 
3. Select **Save**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
