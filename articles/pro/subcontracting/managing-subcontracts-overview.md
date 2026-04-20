---
title: Subcontract management in Project Operations
description: Learn the end-to-end subcontract management process in Project Operations. Discover how to create, manage, and verify subcontracts for project-based organizations.
author: rumant
ms.date: 02/04/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract management in Project Operations

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article provides an overview of the end-to-end subcontract management process in project-based organizations. Subcontracting for services typically follows the business process flow that the following diagram shows.

:::image type="content" source="../media/SubcontractingProcessFlow.png" alt-text="Screenshot of the subcontracting process flow diagram.":::

The following list provides a step-by-step description of the subcontracting process.

1. The project manager creates a subcontract with a vendor. By default, the price lists that are attached to the vendor record are used for the subcontract. The vendor account has a relationship type of **Vendor** or **Supplier**.
1. The project manager can itemize all the purchases as line items on the subcontract. Subcontract lines can be for time, expenses, or products. The transaction class of the subcontract line determines what the line is for.
1. The vendor account manager and the project manager can iterate over the subcontract. Pricing can be adjusted in the purchase price lists that are attached to the subcontract.
1. At this point or later in the process, if the subcontract line is for time, the vendor account manager associates vendor contacts with each subcontract line. This association provides information to the project manager who is working on the subcontract. When a vendor contact is associated with a subcontract line, the system automatically creates a bookable resource from the contact, if a bookable resource doesn't already exist.
1. The billing method on each subcontract line can be **Fixed Price** or **Time and Material**. For fixed-price subcontract lines, a milestone-based invoice schedule is set up.
1. After you set up the subcontract and complete the negotiation, confirm it. You can't edit confirmed subcontracts but if changes occur, you can 'reopen for edits' a subcontract. This action sets the status from **Confirmed** back to **Draft** and negotiation can be reopened.
1. When you create a generic team member on a project, you can associate the team member to a subcontract line. This association indicates the need to staff the generic team member with subcontractor capacity.
1. You can create named team members directly on a project or create them by booking them through the resource scheduling experiences. If a named project team member is a contract worker, you can associate this team member to a subcontract line. This association draws down the available capacity on a subcontract line.
1. Subcontractor resources can log time, expenses, and material usage on projects and project tasks, and then submit for approval. This process is similar for employees. When you record time, a contract worker can select a specific subcontract and subcontract line.
1. Upon approval, time approved by subcontracts records project cost actuals based on the purchase price of the contract worker or the role they performed on the project.
1. You can record vendor invoices and vendor invoice line items in the system for the work performed by vendor resources or products delivered by the vendor. Vendor invoice lines must be specific to a project and for a transaction class of time, expense, product/material, milestone, or fee. Optionally, vendor invoice lines can reference a subcontract line.
1. The system automatically associates all cost actuals that match the subcontract line and project to the vendor invoice. This association facilitates a three way match and verification process.
1. The project manager can then review the automatically matched project actuals, remove or add other project cost actuals, and complete the verification process.
1. Completing the verification process on all lines marks the vendor invoice as **Ready for Payment**. At this stage, the vendor invoice and lines can be transferred to an Accounting or Payables system to process the payment to the vendor. Previously recorded project costs are reversed and actual costs from the vendor invoice line are recorded on the project.

    > [!IMPORTANT]
    > **Fixed Price** subcontracts are currently not supported for _resource/non-stocked based scenarios_ in Project Operations.

## Quantity-based subcontract lines and work-based subcontract lines

A subcontract line can be quantity-based or work-based.

When a subcontract line is **quantity-based**, you can use the quantity you're purchasing on the subcontract line for time, expense, or material on any project.

When a subcontract line is **work-based**, the subcontract line maps to a body of work represented by a node in the project plan. The value of the subcontract line is the sum of all the components that are required to deliver that body of work. These components are modeled as subcontract line details and can be a collection of time, expense, or materials. For a work-based subcontract line, the subcontract line is also dedicated to a single project. Project Operations doesn't currently support these types of subcontracts.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
