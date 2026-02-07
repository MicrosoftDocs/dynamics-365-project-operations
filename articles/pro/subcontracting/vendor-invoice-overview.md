---
title: Vendor invoicing - Concept and creation
description: Learn how to create and manage vendor invoices in Microsoft Dynamics 365 Project Operations. Explore concepts, scenarios, and step-by-step guidance.
author: rumant
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Vendor invoicing - Concept and creation

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Use vendor invoicing in Microsoft Dynamics 365 Project Operations to record costs from deliveries of services and materials on a project by vendors.

When you subcontract services and materials to a vendor, the subcontract represents the contractual agreement with that vendor. As the vendor delivers the services, or the materials arrive and are used on project tasks, you record costs on the project. Periodically, the vendor sends invoices that you verify and match with costs you recorded on the project. After you complete the verification process, you confirm and release the vendor invoice for payment.

## Scenarios for use

Use vendor invoices in Project Operations to support two distinct scenarios.

### Customers use the full subcontracting experiences

Vendor invoice experiences provide a way to verify and match time entries, material usage, and expense entries that reference subcontracted components with vendor invoice lines. Use this process to verify the accuracy of the vendor invoice lines. After you complete the verification process and confirm the vendor invoice, the application reverses the actuals that approved time, expense, and material usage logs recorded, and creates new cost actuals by using the vendor invoice lines.

### Customers don't use the full subcontracting experiences but want to have a unified view of costs on projects in Project Operations

If you're tracking the subcontract process in a third-party system, you can record costs from that third-party system to Project Operations by creating vendor invoices that don't reference subcontracts. In this way, your project managers can have single, unified view of all costs on a given project.

## Creation of vendor invoices in Project Operations

Create vendor invoices in two ways:

- From the vendor invoice list page or the details page for a single vendor invoice
- From the subcontract list page or the details page for a single subcontract

### Creation from the vendor invoice list page or details page

1. Go to **Purchasing** \> **Vendor invoices**.
1. On the vendor invoice list page or the details page for a single vendor invoice, select **New** to create a new vendor invoice.

Vendor invoices that you create this way can also reference a subcontract.

### Creation from the subcontract list page or details page

1. Go to **Purchasing** \> **Subcontracts**.
1. Select one or more subcontracts.
1. On the subcontract list page or the details page for a single subcontract, select **Create vendor invoice** to create a new vendor invoice.

The system creates a new vendor invoice in **Draft** status for each subcontract that you selected.

Vendor invoices that you create in this way always reference the subcontract on the vendor invoice header. Each line on the subcontract that uses the Time and material billing method creates a line on the vendor invoice. Each line on the subcontract that uses the Fixed price billing method creates a line on the vendor invoice for every subcontract line milestone that has a status of **Ready to invoice**.

The following fields and related records are copied from the subcontract to the header of the vendor invoice:

- Vendor
- Related price lists are copied to the vendor invoice as price lists
- Currency
- Contracting unit
- Payment terms

For Time and material subcontract lines, the following fields and related records are copied from the subcontract line to the vendor invoice line:

- Subcontract and subcontract line references
- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task
- Bookable resource

For Fixed price subcontract lines, the following fields are copied from the subcontract line and subcontract line milestone to the vendor invoice line:

- Subcontract and subcontract line references
- Transaction class. By default, the value is **Milestone**.
- Milestone name and amount are copied from the related subcontract line milestone.
- The user can select a project and task on the vendor invoice line.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
