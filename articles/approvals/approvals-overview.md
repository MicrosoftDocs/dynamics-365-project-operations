---
title: Approvals overview
description: This topic provides information about working with approvals in Project Operations.
author: stsporen
manager: Annbe
ms.date: 10/05/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: stsporen
---

# Approvals overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Time and Expense submissions move through an approval workflow. After the entries are approved, transactions are recorded in actuals or time is booked in the schedule.

## Approvals workflow
When you create and submit a time or expense entry, an approval entry is created. The Project approver or your manager reviews and approves your entry. If the entry is related to a project, when it's approved, the actuals will be created. This allows the cost and billing to be tracked. 

## Approve an entry
The **Approvals** form allows you to switch between different views so that you can view the different types of approvals.
  
1. Go to the **Approvals** form and select **Expenses**, **Time**, or **Recalls**.
2. Review each approval, and select the ones you want to approve.
3. Select **Approve** to approve the selected entries.
The system will process these entries and create actuals or a booking.

## Reject an entry
As the Project approver, you may have to send an entry back to a user for correction.
  
1. Go to the **Approvals** form and select the entry to reject. 
2. Select **Reject**.
3. Optional - Add a comment in the **Rejection Comments** dialog to inform the user why the entry is being rejected.
4. Select **OK**. The entry will be returned to the user.
  
## Recall entries
At some point, you might need to recall a submitted entry. If the entry has not been approved, it will be returned immediately. An approved entry however, may have a material impact. The Project approver is required to approve the recall in order to reverse the transaction in Actuals.

## Specify Project approvers
Each project has a number of project team members. You can specify which team members are also Project approvers.

1. Go to the **Projects** form and open the project from the list.
2. On the **Team** tab, select the team member who will be a Project approver and then select **Edit**.
3. Set the **Project Approver** field to **Yes**.
4. Select **Save**.
5. Repeat steps 2-4 to add additional Project approvers.

## Configure the user's manager

1. Go to **Settings** > **Security** > **Users**.
2. Select the user to whom you are assigning a manager and in the **Organization Information** area, select the manager from the list. 
3. Select **Save**.


