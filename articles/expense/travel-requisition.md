---
title: Travel requisitions
description: Learn how to create, submit, and manage travel requisitions to pre-authorize expenses and ensure compliance with organizational policies.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Travel requisitions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

A travel requisition lists the expenses incurred for the purpose of travel. Submit a travel requisition for review. Use it to authorize expenses.

You might need to submit a travel requisition before incurring any expense that you charge to the organization. This requirement applies regardless of whether you charge expenses to a corporate credit card, spend cash that you received from a cash advance, or incur out-of-pocket expenses that the organization reimburses.

Use travel requisitions and policies to help manage organization expenditures. For example, if your organization is working on a fixed-price project that requires travel, the travel expenses of the project's team members must fit within the project budget. By requiring that travel expenses be approved before incurred, the organization can help make sure that the project remains within budget.

## Configuration

You can configure travel requisitions as mandatory by enabling the **Pre-authorization of travel is mandatory** parameter in Expense Management Parameters.

## Create and submit a travel requisition

To create and submit a travel requisition, follow these steps:

1. Go to **My expenses: Travel Requisition**, and select **New travel Requisition**.
1. Enter a purpose and destination for the requisition.
1. In the  **Travel description** field, enter any additional information.
1. For each of the expected expenses, such as Flight, meals, or car rental, create an expense line item. Include the estimated date, estimated amount, and the currency for each expense.
1. When finished adding the expected expenses, select **Save**.
1. When ready to submit the travel requisition, select **Workflow** > **Submit**.

You can view your approved travel requisitions under **My Expenses: Travel Requisition**.

## View available travel requisitions

You can view all of your travel requisitions under **My Expenses: Travel Requisitions**.

## Approve travel requisitions

Select the travel requisition that you want to approve, and then select **Workflow** > **Approve**.  

## Submit an expense report using your approved travel requisition

1. Create a new expense report. In the expense report header, select **Map to Travel requisition** and choose from the list of approved travel requisitions.
1. The **Travel requisition amount** field automatically updates in the expense report header.
1. Add each expense incurred for the trip.
If the **Pre-authorized** field is enabled, the reconciled amount and authorized amount for the specific expense category update.

> [!NOTE]
> When you map an expense report to an approved travel requisition, the transaction amount can't be greater than the authorized amount.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
