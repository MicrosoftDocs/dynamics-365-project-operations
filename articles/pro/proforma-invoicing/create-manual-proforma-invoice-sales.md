---
title: Create a manual proforma invoice - lite
description: This topic provides information about creating a manual proforma invoice in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/19/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Create a manual proforma invoice - lite

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, proforma invoices can be created manually as needed. You can manually create a proforma invoice from the **Project Contracts** list page or from the **Project Contract** details page.

##  Project Contracts list page

From **Project Contracts** list page, select one or more project contracts, and create invoices for all of the selected records.

The system checks to see which of the selected project contracts has a **Ready to Invoice** backlog dated before today's date. From those contracts, the system creates draft proforma invoices. If a project contract has multiple customers, there may be one invoice created per customer, and multiple invoices per project contract.

All of the created project invoices are available on the **Invoice** page in the **Billing** section of the **Sales** area.

## Project Contract details page

A proforma invoice can also be created from the **Project Contract** details page, which creates the invoice for that specific project contract. The system verifies that the project contract has a **Ready to Invoice** backlog dated before today's date. From these contracts, the system creates draft proforma invoices based on the number of customers on each contract line.

When there's a single proforma invoice created, the **Invoice** page opens. If multiple invoices are created for that project contract, the **Invoices** list page opens to show all of the created invoices.
