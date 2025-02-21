---
title: Manage billing backlog
description: This article provides information about how to view and work with the billing backlog in Project Operations.
author: rumant
ms.date: 02/21/2025
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage billing backlog

_**Applies To:** Project Operations for resource/non-stocked based scenarios

Dynamics 365 Project Operations has dedicated views to help manage the billing backlog. To manage the billing backlog, select the links in the **Sales** area, under **Billing**. 

The following views available:

- Retainers and Advances
- Available Retainers and Advances
- Fixed Price Milestones
- Time and Material Billing Backlog

## Retainers and Advances

The **Retainers and Advances** view lists the retainers and advances across all project contracts. After a retainer or advance is invoiced, the amount of the advance becomes available to use.

## Available Retainers and Advances

The **Available Retainers and Advances** view lists all available retainers and advances across all project contracts. After a retainer or advance is invoiced, the amount of the advance becomes available to use and is added to the list. After the amount of the retainer or advance is used completely, it's removed from the list.

## Fixed Price Milestones

The **Fixed Price Milestones** view lists all fixed price milestones across all project contract lines. From this view, single or multiple milestones can be marked as **Ready to invoice** or **Not ready to invoice**. Marking a milestone as **Ready to invoice** makes it available to be put on a draft invoice.

When multi-customer contract lines have a fixed price billing method, a milestone is created for each customer on the contract line. A milestone can be created and then split into individual customer-specific milestone records. This split is internal and in accordance with the billing percentage split defined for each customer on the contract line. In the **Fixed Price Milestones** view, you will see the individual customer-specific milestone records. Each of these milestone records can be marked as **Ready to Invoice** separately from this view. When one or more of the related milestone splits are marked as **Ready to Invoice**, the header status updates to **In Progress** from **Not Started**. When all of the milestone splits are invoiced, the header milestone status updates to **Completed**.

A milestone on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on the record is updated to **Customer Invoice Posted**. 

> [!NOTE] 
> Do not update this status value by using custom code. Project Operations doesn't function correctly when these status values are updated with custom code.

## Time and Material Billing Backlog

The **Time and Material Billing Backlog** view lists all unbilled sales actuals across all project contracts in the system that haven't been invoiced. 

> [!NOTE]
> Unbilled sales actuals may have the adjustment status set to **Unadjustable** or **Adjusted** during contract confirmation, invoice confirmation or when invoice line details are updated. Transactions with an adjustment status of **Adjusted** or **Unadjustable** are not invoiceable. Such transactions are excluded from the Time and material billing backlog view for ease of invoicing.
 
Single or multiple unbilled sales actuals can be marked as **Ready to Invoice** or **Not Ready to Invoice** from this view. Marking an unbilled sales actual as **Ready to Invoice** makes it available to be put on a draft invoice.


Unbilled sales actuals with a **Not-to-Exceed** status of **Failed** can't be marked as **Ready to Invoice**. If the actuals need to be marked as **Ready to Invoice**, reset the status on other actuals on the contract line that are committed, and then re-evaluate the **Not-to-Exceed** status.

If multi-customer contract lines have a time and material billing method, when time and expenses are approved, one unbilled sales actual is created for each customer on the contract line according to the billing percentage split defined for each of the customers. In the **Time and Material Billing Backlog** view, you will see these individual customer-specific unbilled sales actuals. Each of these unbilled sales actual records can be marked as **Ready to Invoice** separately from this view.

An unbilled sales actual that's on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on this record is updated to **Customer Invoice Posted**. 

> [!NOTE] 
> Do not update this status value by using custom code. Project Operations doesn't function correctly when these status values are updated with custom code.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
