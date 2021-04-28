---
title: Vendor invoice integration
description: This topic provides information about vendor invoice integration in Project Operations for resource/ non-stocked scenarios.
author: sigitac
manager: Annbe
ms.date: 4/27/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Vendor invoice integration

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project related procurement in Project Operations for resource/ non-stocked scenarios can be recorded using Pending vendor invoice document in Accounts Payable > Invoices > Pending vendor invoices. See [Purchase non-stocked materials using a pending vendor invoice | Microsoft Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/procurement/pending-vendor-invoices) for more details.

Important!
Before you use the functionality described in this topic, review and apply the required configurations. For more information, see [Enable non-stocked materials and pending vendor invoices](https://docs.microsoft.com/en-us/dynamics365/project-operations/procurement/configure-materials-nonstocked).

In Project Operations for resource based/ non stocked scenarios, project related vendor invoices are posted using special posting rules:

1. Project related cost (including non-recoverable tax) is not immediately posted to project cost account in general ledger, but instead is posted to **Procurement integration account**. This account is configured in Project management and accounting > Setup > Project management and accounting parameters, Project Operations on Dynamics 365 Customer engagement tab.
2. Dual-write synchronizes vendor invoice details to Dataverse using the following table maps:

     - **Project Operations integration project vendor invoice export entity (msdyn_projectvendorinvoices)** synchronizes vendor invoice header information. Note that only vendor invoices with at least one line with Project ID filled in are synchronized to Dataverse.
     - **Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines)** synchronizes vendor invoice line information. Note that only lines with Project ID filled in are synchronized to Dataverse.
     - Vendor invoice details in Dataverse are not editable.

3. Tax subledger, vendor subledger and other financial postings are recorded as applicable in Dynamics 365 Finance, at the time of vendor invoice posting.

![Vendor invoice integration](DW7VendorInvoice.png)

As record gets written to Vendor invoice entities in Dataverse, system triggers automated approval process of these records. If needed, automated approval process status can be reviewed in Dataverse by navigating to Advanced settings > System > System jobs. Once approval is complete, system creates Material transaction class records in the Actuals entity.

Material related actuals are then processed using dual-write table map **Project Operations integration actuals (msdyn_actuals)**. See [Project estimates and actuals]( resource-dual-write-estimates-actuals.md) for more details.

**Import from staging** periodic process creates vendor invoice related Project Operations integration journal lines. Offset account is defaulted to Procurement integration account. Posting integration journal, clears this account balance for the vendor invoice transaction and moves line amount to project cost account. System also creates Project subledger transactions for downstream invoicing and revenue recognition purposes.
