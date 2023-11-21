---
title: Travel requisitions
description: This article provides information about travel requisitions.
author: suvaidya
ms.date: 10/01/2020
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Travel requisitions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A travel requisition lists the expenses that will be incurred for the purpose of travel. A travel requisition is submitted for review and can be used to authorize expenses.

You may be required to submit a travel requisition before you incur any expense that is charged to the organization. This requirement applies, regardless of whether you charge expenses to a corporate credit card, spend cash that you received from a cash advance, or incur out-of-pocket expenses that will be reimbursed by the organization.

Travel requisitions and policies can be used to help manage organization expenditures. For example, if your organization is working on a fixed-price project that requires travel, the travel expenses of the project's team members must fit within the project budget. By requiring that travel expenses be approved before they are incurred, the organization can help make sure that the project remains within budget.

## Configuration 

Travel Requisitions can be configured as "mandatory" by enabling the "Pre-authorization of travel is mandatory" parameter in Expense Management Parameters. 

## Create and submit a travel requisition

1. Go to **My expenses: Travel Requisition**, and select **New travel Requisition**.
2. Enter a purpose and destination for the requisition.
3. In the  **Travel description** field, enter any additional information. 
4. For each of the expected expenses, such as Flight, meals, or car rental, create an expense line item. Include the estimated date, estimated amount, and the currency for each expense. 
5. When you have finished adding the expected expenses, select **Save**.
6. When you are ready to submit the travel requisition, select **Workflow** > **Submit**.

You can view your approved travel requisitions under **My Expenses: Travel Requisition**. 

## View available travel requisitions

You can view all of your travel requisitions under **My Expenses: Travel Requisitions**.

## Approve travel requisitions

Select the travel requisition that you want to approve, and then select **Workflow** > **Approve**.  

## Submit an expense report using your approved travel requisition

1. Create a new expense report and in the expense report header, and from the list of approved travel requisitions, select **Map to Travel requisition**.
2. The **Travel requisition amount** field is automatically updated in the expense report header.
3. Add each expense incurred for the trip. 
If the **Pre-authorized** field is enabled, the reconciled amount and authorized amount for the specific expense category will be updated.

> [!NOTE]
> When you map an expense report to an approved travel requisition, the transaction amount can't be greater than the authorized amount. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
