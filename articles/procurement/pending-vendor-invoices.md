---
title: Purchase non-stocked materials using Pending vendor invoice document
description: This topic provides information about how to record pending vendor invoices in Project operations for resource/non-stocked based scenarios. 
author: sigitac
manager: tfehr
ms.date: 04/12/2021
ms.topic: article
ms.prod:
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Purchase non-stocked materials using Pending vendor invoice document

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

As company procures non-stocked materials, it's cost can be immediately recorded against the project. For example, Contoso Robotics US is performing equipment renewal project and needs software licenses. These licenses are procured from third party vendor. 
Accounts payable clerk using Dynamics 365 Finance records pending vendor invoice document and attributes license cost directly against equipment renewal project. 

**!Note Review and apply required configurations as described in [Enable non-stocked materials and pending vendor invoices | Microsoft Docs] (configurematerials_nonstocked.md) in your environment before using functionality described in this article. 

## Post project related pending vendor invoice document

Pending vendor invoices can be recorded in Accounts payable > Invoices > Pending vendor invoices. 
1. Create a new invoice by using New button. 
2. Select the vendor in Invoice account field. Fill in vendor invoice identification in the Number field.
3. Add a line to vendor invoice. In Item number field select non-stocked item purchased from the vendor. Note that Procurement category based vendor invoice lines cannot be recorded against the project. 
4. Fill in quantity purchased. System will default Unit price based on non-stocked item price configuration. Verify total amount and other required details on the line
5. In line details open Project tab:
    a. Select Project ID this item will be recorded to.
    b. Optionally select Activity number, update project category and line property.
 6. Post pending vendor invoice. Upon posting, system will record:
    a. Vendor balance amount
    b. Sales tax amount.
    c. Cost against the project will be recorded to Procurement integration account.
    d. Project actual transaction in Dataverse. This transaction will be further processed using [Project Operations Integration journal](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/project-operations-integration-journal) Posting this journal will move amount from Procurement integration account to project cost account.

    
   
 


