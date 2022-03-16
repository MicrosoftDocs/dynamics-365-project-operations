---
title: Vendor Invoicing - Concept and Creation  
description: This topic describes the concept of vendor invoice, scenarios for usage and how to create vendor invoices in Project Operations.
author: rumant
ms.date: 03/15/2022
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Vendor Invoicing - Concept and Creation  

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Vendor Invoicing in Project Operations can be used to record costs from deliveries of services and/or materials on a project by vendors. 

When services and/or materials are subcontracted to a vendor, a subcontract represents the contractual agreement with the vendor. As the vendor delivers the services or the materials are received and used on project tasks, costs are recorded on the project. Periodically, the vendor sends invoices that are matched and verified with costs recorded on the project. Once the verification process is complete, vendor invoice is confirmed, and it is released for payment. 

Vendor invoices in Dynamics 365 Project Operations can be used to support 2 distinct scenarios:

### Customers who use the full subcontracting experiences: 
Vendor Invoice experiences provide a way to verify and match time entries, material usage and expense entries that reference subcontracted components with vendor invoice lines. This verification process can be used as a tool to verify the accuracy of the vendor invoice lines. Once this verification process is completed and the vendor invoice is confirmed, the application will reverse the actuals recorded by approved time, expense and material usage logs and create new cost actuals using the vendor invoice lines. 
### Customers that do not use the full subcontracting experiences but would like to have a unified view of costs on projects in Project Operations: 
If you are tracking the subcontract process in a different 3rd party system, you can create vendor invoices that do not reference subcontracts as way to record those costs from the 3rd party system to Project Operations, so your project managers can have single, unified view of all costs on a given project.

## Creation of Vendor invoices in Project Operations:
Vendor invoices can be created in 2 ways:
1.	From the Subcontract list page or from the main form a single subcontract
2.	From the list page of vendor invoices or from the main form a single vendor invoice
### Creation from the Vendor Invoice list or main pages:
1.	Navigate to Purchasing -> Vendor invoices
2.	Use the +New on the Vendor Invoice list page or on the details page of single vendor invoice to create a new vendor invoice. 
3.	Vendor invoices created in this way can also reference a subcontract. 
### Creation from a Subcontract:
1.	Navigate to Purchasing -> Subcontracts
2.	Select a single or multiple subcontracts and use the Create Vendor Invoice on the Subcontract list page or on the details page of single Subcontract to create a new vendor invoice. 
3.	A new vendor invoice in draft status will be created for each selected subcontract.

Vendor invoices created in this way will always reference the subcontract on the vendor invoice header. Each line on the subcontract with a time and Material billing method will result in a line on the vendor invoice. For each line on the subcontract with a Fixed Price billing method, there will be a vendor invoice line created for every subcontract line milestone that is in status “ready to invoice”. 

The following fields and related records on the header of a vendor invoice will be copied from the Subcontract
1.	Vendor
2.	Related Price Lists on the subcontract will be coped to the Vendor Invoice as Price Lists
3.	Currency
4.	Contracting Unit
5.	Payment Terms

For time and material subcontract lines, the following fields and related records will be copied from the subcontract line to the vendor invoice line:
1.	Subcontract and subcontract line references 
2.	Transaction Class
3.	Role
4.	Transaction Category
5.	Product fields
6.	Project
7.	Task
8.	Bookable Resource 

For Fixed price subcontract lines, the following fields on the vendor invoice line will be copied from the subcontract line and subcontract line milestone. 
1.	Subcontract and subcontract line references 
2.	Transaction Class will default to Milestone
3.	Milestone name and amount will be copied from the related subcontract line milestone
4.	User will be able to select a project and task on the vendor invoice line.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
