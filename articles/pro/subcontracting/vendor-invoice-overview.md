---
title: Vendor invoicing - Concept and creation
description: This article describes the concept of vendor invoices, scenarios for use, and how to create vendor invoices in Microsoft Dynamics 365 Project Operations.
author: rumant
ms.date: 12/15/2023
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoicing - Concept and creation

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Vendor invoicing in Microsoft Dynamics 365 Project Operations can be used to record costs from deliveries of services and/or materials on a project by vendors.

When services and/or materials are subcontracted to a vendor, a subcontract represents the contractual agreement with that vendor. As the vendor delivers the services, or the materials are received and used on project tasks, costs are recorded on the project. Periodically, the vendor sends invoices that are verified and matched with costs that are recorded on the project. After the verification process is completed, the vendor invoice is confirmed and released for payment.

## Scenarios for use

Vendor invoices in Project Operations can be used to support two distinct scenarios.

### Customers use the full subcontracting experiences

Vendor invoice experiences provide a way to verify and match time entries, material usage, and expense entries that reference subcontracted components with vendor invoice lines. This process can be used to verify the accuracy of the vendor invoice lines. After the verification process is completed and the vendor invoice is confirmed, the application will reverse the actuals that were recorded by approved time, expense, and material usage logs, and create new cost actuals by using the vendor invoice lines.

### Customers don't use the full subcontracting experiences but want to have a unified view of costs on projects in Project Operations

If you're tracking the subcontract process in a third-party system, you can record costs from that third-party system to Project Operations by creating vendor invoices that don't reference subcontracts. In this way, your project managers can have single, unified view of all costs on a given project.

## Creation of vendor invoices in Project Operations

Vendor invoices can be created in two ways:

- From the vendor invoice list page or the details page for a single vendor invoice
- From the subcontract list page or the details page for a single subcontract

### Creation from the vendor invoice list page or details page

1. Go to **Purchasing** \> **Vendor invoices**.
2. On the vendor invoice list page or the details page for a single vendor invoice, select **New** to create a new vendor invoice.

Vendor invoices that are created in this way can also reference a subcontract.

### Creation from the subcontract list page or details page

1. Go to **Purchasing** \> **Subcontracts**.
2. Select one or more subcontracts.
3. On the subcontract list page or the details page for a single subcontract, select **Create vendor invoice** to create a new vendor invoice.

A new vendor invoice in **Draft** status is created for each subcontract that you selected.

Vendor invoices that you create in this way always reference the subcontract on the vendor invoice header. Each line on the subcontract that has a Time and material billing method will cause a line to be created on the vendor invoice. Each line on the subcontract that has a Fixed price billing method will cause a line to be created on the vendor invoice for every subcontract line milestone that has a status of **Ready to invoice**.

The following fields and related records will be copied from the subcontract to the header of the vendor invoice:

- Vendor.
- Related price lists will be copied to the vendor invoice as price lists.
- Currency.
- Contracting unit.
- Payment terms.

For Time and material subcontract lines, the following fields and related records will be copied from the subcontract line to the vendor invoice line:

- Subcontract and subcontract line references
- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task
- Bookable resource

For Fixed price subcontract lines, the following fields will be copied from the subcontract line and subcontract line milestone to the vendor invoice line:

- Subcontract and subcontract line references.
- Transaction class. By default, the value will be **Milestone**.
- Milestone name and amount will be copied from the related subcontract line milestone.
- The user will be able to select a project and task on the vendor invoice line.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
