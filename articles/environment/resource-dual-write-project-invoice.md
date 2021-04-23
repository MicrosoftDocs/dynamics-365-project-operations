---
title: Project invoice integration
description: This topic provides information about Project Operations dual-write integration for customer invoicing.
author: sigitac
ms.date: 04/23/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Project invoice integration

This topic provides information about Project Operations dual-write integration for customer invoicing.

In Project Operations, Project manager manages the project billing backlog and creates proforma invoice to the customer in Dataverse. Based on this proforma invoice, Accounts receivable clerk/project accountant creates a customer-facing invoice. Dual-write integration ensures proforma invoice details are synchronized to Finance and Operations apps. Once customer facing invoice is posted, system updates relevant Project Actuals in Dataverse with the accounting detail. Picture below provides high level conceptual overview of this integration.

![Project invoice integration](./media/DW5Invoicing.png)

Once Project manager confirms Proforma invoice in Dataverse, system synchronizes Proforma invoice header information to Finance and Operations apps using dual-write table map **Project invoice proposal V2 (invoices)**. This integration is one-way from Dataverse to Finance and Operations apps. Creating or deleting Project invoice proposals directly in Finance and Operations apps is not supported.

Invoice confirmation in Dataverse also triggers business logic to create billing related records in Actuals entity.  These records are synchronized to Finance and Operations using dual-write table map **Project Operations integration actuals (msdyn\_actuals).** See [Project estimates and actuals]( resource-dual-write-estimates-actuals.md) for more details. 

Project invoice proposal lines are created by **Import form staging** periodic process based on the billed sales actuals details in the Actuals staging table. See  [Manage project invoice proposals | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/invoicing/format-update-project-invoice-proposals#create-project-invoice-proposals). 
