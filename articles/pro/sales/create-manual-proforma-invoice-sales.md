---
title: Creating a manual proforma invoice
description: This topic provides information about creating a manual proforma invoice in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/19/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Creating a manual proforma invoice

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, proforma invoices can be created manually as needed. You can manually create a proforma invoice from the **Project Contracts** page or from the **Project Contract Details** page of a single contract.

##  Project Contracts page

From **Project Contracts** page, select one or more project contracts, and create invoices for all of the selected records.

The system will check which of the selected project contracts has a **Ready to Invoice** backlog that is dated before the current date and will create draft proforma invoices. If a project contract has multiple customers, there may be one invoice created per customer and therefore multiple invoices per project contract.

All of the created project invoices will be available on the **Invoice** page in the **Billing** section of the **Sales** area of Project Operations.

## Project Contract Details page

A proforma invoice can also be created from the **Project Contract Details** page which will create the invoice for that specific project contract. The system verifies that the project contract has a **Ready to Invoice** backlog that is dated before the current date and then creates draft proforma invoices based on the number of customers on each contract line of the project contract.

When there is a single proforma invoice created, the **Invoice** page opens. If there are multiple invoices created for that project contract, then the **Invoices** list page opens to show all of the created invoices.
