---
title: Manage project billing backlog 
description: This article provides information about the various views available to use when managing the billing backlog on projects.
author: poojafandan
ms.date: 11/26/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Manage project billing backlog 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

Dynamics 365 Project Operations has dedicated views to help manage the billing backlog. To manage the billing backlog, select the links in the **Sales** area, under **Billing**. 

The following views available:

- Retainers and Advances
- Available Retainers and Advances
- Fixed Price Milestones
- Product Billing Backlog
- Time and Material Billing Backlog

## Retainers and Advances

The **Retainers and Advances** view lists all the retainers and advances across all project contracts in the system. After a retainer or advance is invoiced, the amount of the advance becomes available to use.

## Available Retainers and Advances

The **Available Retainers and Advances** view lists all available retainers and advances across all project contracts in the system. After a retainer or advance is invoiced, the amount of the advance becomes available to use and is added to the list. After the amount of the retainer or advance is used completely, it's removed from the list.

## Fixed Price Billing

In Fixed price billing arrangements, the contract negotiation involves either billing based on completed milestones or billing based on % complete of a milestone. 

- Milestone based billing is to enable billing based on completion of a milestone. 
- Progress based billing is to enable billing based on progress or % complete of a milestone.

When the project-based contract line has a Fixed billing method, you can create a milestone based or progress based invoice schedule. Complete the following steps to automatically generate this schedule for a fixed set of milestones that are equally distributed for the calendar period.

1. Go to Settings > invoice frequencies and set up an invoice frequency.
1. Add a new Contract line and give the contract line a name, then select Fixed price as the billing method. The field Invoice schedule type appears, in which you have option to select Milestone based or Progress based invoice schedule.
1. Once the contract line is created, you can go to Invoice schedule tab, select values in the Billing start and Invoice Frequency fields.
1. On the sub grid, select Generate Periodic Milestones.

Fixed price milestones can also be generated manually when they aren't periodically split. To create a milestone manually, open the Fixed price quote line where you need to create a milestone. On the Invoice Schedule tab, on the sub grid, select + Create new milestone and enter the required information.

## Fixed Price Milestones 

The **Fixed Price Milestones** view lists all fixed price milestones across all project contract lines in the system. Single or multiple milestones can be marked as **Ready to invoice** or **Not ready to invoice** from this view. Marking a milestone as **Ready to invoice** makes it available to be put on a draft invoice. Updating the progress percentage (%) of a progress-based milestone and marking the next invoice status of a progress-based milestone as **Ready to invoice** creates a new milestone with the value of the milestone calculated as a % of progress that is marked as being ready to invoice. 

When multi-customer contract lines have a fixed price billing method, a milestone is created for each customer on the contract line. A milestone can be created and then split into individual customer-specific milestone records. This split is internal and in accordance with the billing percentage split defined for each customer on the contract line. In the **Fixed Price Milestones** view, you see the individual customer-specific milestone records. Each of these milestone records can be marked as **Ready to Invoice** separately from this view. When one or more of the related milestone splits are marked as **Ready to Invoice**, the header status is updated to **In Progress** from **Not Started**. When all of the milestone splits are invoiced, the header milestone status is updated to **Completed**.

When contract lines have a fixed price billing method with a progress-based invoice schedule type, a progress-based set of milestones are created for the contract line. In the **Fixed Price Milestones** view, you see the individual milestone records that represent the value of the progress-based milestone that can be invoiced. Each of these milestone records can be marked as **Ready to Invoice** separately from this view. When one or more of the related milestone splits are marked as **Ready to Invoice**, the progress-based milestone's billing status is updated to **In Progress** from **Not Started**. When all the progress-based milestone's value are invoiced, the header milestone status is updated to **Completed**.

A milestone on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. On a progress-based milestone, it's the **Next invoice status** that shows this value. When the draft invoice is confirmed, the billing status on the milestone is updated to **Customer Invoice Posted** and the **Next invoice status** of the progress-based milestone is updated to **Not ready to invoice**. Don't update this status value using custom code. Project Operations doesn't function correctly when these status values are updated with custom code. 

## Billing status updates on the various types of milestones


### Scenario 1: Single Customer, Completed Milestones

| Event | Billing Status |
| --- | --- |
| **Contract creation** | Not Ready to invoice |
| **Update milestone status to Ready to Invoice** | Ready to invoice |
| **Draft Invoice creation** | Customer invoice created |
| **Invoice confirmation** | Customer invoice posted |

### Scenario 2: Multiple Customers, Completed Milestones

| Event | Header Billing Status | Milestone Billing Status
| --- | --- | --- |
| **Contract creation** | Not Started | Not ready to invoice |
| **Update milestone status to Ready to Invoice** | In Progress | Ready to invoice |
| **Draft Invoice creation** | In Progress |Customer invoice created |
| **Invoice confirmation for one customer** | In Progress | Combination of Customer invoice posted and Customer invoice created |
| **Invoice confirmation for all customers** | Completed | Customer invoice posted |


### Scenario 3: Single Customer, Progress - based Milestones

| Event | Next invoice status| Header Billing Status | Milestone Billing Status
| --- | --- | --- |--- |
| **Contract creation** | Not ready to invoice | Not Started | Not ready to invoice |
| **Update Next invoice status to Ready to Invoice** | Ready to invoice | In Progress | Ready to invoice |
| **Draft Invoice creation** | Customer invoice created | In Progress | Customer invoice created |
| **Invoice confirmation** | Not ready to invoice | In Progress | Combination of Customer invoice posted and Not ready to invoice |
| **All milestones invoiced for this progress - based milestone header** | Not ready to invoice | Completed | Customer invoice posted |

### Scenario 4: Multiple Customers, Progress - based Milestones

| Event | Next invoice status| Header Billing Status | Milestone Billing Status
| --- | --- | --- |--- |
| **Contract creation** | Not ready to invoice | Not Started | Not ready to invoice |
| **Update Next invoice status to Ready to Invoice** | Ready to invoice | In Progress | Ready to invoice |
| **Draft Invoice creation** | Customer invoice created | In Progress | Combination of Customer invoice created and Not ready to invoice  |
| **Invoice confirmation for one customer** | In Progress | Combination of Customer invoice posted, Customer invoice created, and Not ready to invoice |
| **Invoice confirmation for all customers** | In Progress | Combination of Customer invoice posted and Not ready to invoice  |
| **All milestones invoiced for this progress - based milestone header across all customers** | Not ready to invoice | Completed | Customer invoice posted |

## Product Billing Backlog

The **Product Billing Backlog** view lists all product-based contract lines across all project contracts in the system. Single or multiple product-based contract lines can be marked as **Ready to Invoice** or **Not Ready to Invoice** from this view. Marking a product-based contract line as **Ready to Invoice** makes it available to be put on a draft invoice.

A product-based contract line that is on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on this record is updated to **Customer Invoice Posted**. Don't update this status value by using custom code. Project Operations doesn't function correctly when these status values are updated with custom code.

## Time and Material Billing Backlog

The **Time and Material Billing Backlog** view lists all unbilled sales actuals across all project contracts in the system that haven't been invoiced. Single or multiple unbilled sales actuals can be marked as **Ready to Invoice** or **Not Ready to Invoice** from this view. Marking an unbilled sales actual as **Ready to Invoice** makes it available to be put on a draft invoice.

Unbilled sales actuals with a **Not-to-Exceed** status of **Failed** can't be marked as **Ready to Invoice**. If the actuals need to be marked as **Ready to Invoice**, reset the status on other actuals on the contract line that are committed, and then reevaluate the **Not-to-Exceed** status.

If multi-customer contract lines have a time and material billing method, when time and expenses are approved, one unbilled sales actual is created for each customer on the contract line according to the billing percentage split defined for each of the customers. In the **Time and Material Billing Backlog** view, you see these individual customer-specific unbilled sales actuals. Each of these unbilled sales actual records can be marked as **Ready to Invoice** separately from this view.

An unbilled sales actual that is on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on this record is updated to **Customer Invoice Posted**. Don't update this status value using custom code. Project Operations doesn't function correctly when these status values are updated with custom code.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
