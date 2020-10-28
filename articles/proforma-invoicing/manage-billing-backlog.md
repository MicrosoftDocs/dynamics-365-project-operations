---
title: Manage the billing backlog
description: This topic provides information about how to view and work with the billing backlog in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/20/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Manage the billing backlog

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations has two dedicated views to help you work with and manage the billing backlog. They are **Fixed Price Milestones** and **Time and Material Billing Backlog** To select a view, in the **Sales** area of Project Operations, on the left navigation page, select **Billing**. The billing backlog links are stored there.

## Fixed Price Milestones

This view lists all fixed price milestones across all of the project contract lines in the system. Single or multiple milestones can be marked as **Ready to Invoice** or **Not Ready to Invoice** from this view. When you mark a milestone as **Ready to Invoice**, the milestone becomes available for a draft invoice.

When multi-customer contract lines have a fixed price billing method, one milestone is created for each customer on the contract line. The user creates a milestone and that milestone is split into customer=specific milestone records internally, according to the billing percentage split defined for each customer on the contract line. In the **Fixed Price Milestones** view, you will see individual customer-specific milestone records. Each of these milestone records can be marked as **Ready to Invoice** separately from this view. When one or more of the related milestone splits are marked as **Ready to Invoice**, the header moves to a status of **In Progress** from **Not Started**. When all of the milestone splits have been invoiced, the header milestone status becomes **Completed**.

A milestone on a draft invoice is shown in this view with a billing status of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on this record is updated to **Invoice Posted**. Updating this status value by using custom code isn't recommended. Project Operations won't function correctly if these status values are updated with custom code.

## Time and Material Billing Backlog

This view lists all unbilled sales actuals that haven't been invoiced across all project contracts in the system. Single or multiple unbilled sales actuals can be marked as **Ready to Invoice** or **Not Ready to Invoice** from this view. Marking an unbilled sales actual as **Ready to Invoice** makes it available to be put on a draft invoice.

Unbilled sales actuals that have a **Not-to-Exceed** status of **Failed** can't be marked as **Ready to Invoice**. If these actuals need to be marked as such, reset the status on other actuals on the contract line that are committed, and then evaluate the **Not-to-Exceed** status.

In the case of multi-customer contract lines that have a time and material billing method, when time and expenses are approved, an unbilled sales actual is created for each customer on the contract line according to the billing percentage split defined for each customer on the contract line. In the **Time and Material Billing Backlog** view, you'll see these individual customer-specific unbilled sales actuals. Each of these unbilled sales actual records can be marked as **Ready to Invoice** separately from this view.

An unbilled sales actual on a draft invoice is shown in this view with a **Billing Status** of **Customer Invoice Created**. When the draft invoice is confirmed, the billing status on this record is updated to **Customer Invoice Posted**. Updating this status value when it is in this state by using custom code isn't recommended. Project Operations won't function correctly when these status values are updated with custom code.
