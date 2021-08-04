---
title: Subcontracting - October 2021 Release Early Access Scope
description: This topic provides an overview of the October 2021 Release Early Access Scope for Sucbontracting capabilities in Project Operations.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontracting - October 2021 Release Early Access Scope

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_


Subcontracting Project Operations – October 2021 Early Access Scope:

The October 2021 early access release is lighting up portions of the subcontracting capabilities for Project Operations customers. However, this feature set is not ready for Production or live usage. Subcontracting feature set will remain in Preview mode until the full capability set is released. Until the Preview tag is removed in the Docs site, it is strongly advised to not use the Subcontracts capability set for live production scenarios.

As outlined in the overview article, the full scope and vision of subcontracting will take a few releases to land. Below is the outlined scope for October 2021 Early Access:

1.	Project Manager creates a subcontract with a Vendor. Price lists on the subcontract are defaulted from the Price Lists attached to the Vendor record. Vendor is an Account with Relationship type as Vendor or Supplier.

2.	Project Manager can itemize all the purchases as line items on the Subcontract. Subcontract Lines can be for Time, Expense or Products. This is determined by the Transaction class selected on the Subcontract line.

3.	Vendor Account Manager and the Project Manager can iterate over the subcontract. Pricing can be adjusted in the Purchase Price List(s) attached to the Subcontract. 

4.	At this stage or later in the process, Vendor Account Manager associate contacts to each Subcontract line, if the Subcontract line is for Time. This is to indicate to the PM who will be working on subcontract. When associating a Contact to the Subcontract line, the system will automatically create a Bookable Resource from a Contact if it does not exist already. 

5.	Billing Method on the Subcontract line can be Fixed Price or T&M. For Fixed Price Subcontract lines, there is the ability to setup a Milestone based invoice schedule. 

The figure below represents this scope figuratively and contrasts it with the full vision:

![Subcontracting process flow](../media/SubcontractingEAFlow.png)
  
Below is the list of capabilities that will land in monthly updates post-October 2021 EA:
6.	Once the subcontract is setup, it should be confirmed. Confirmed subcontracts cannot be edited but should changes occur, a Subcontract can be ‘reopened for edits’ that moves the status from Confirmed back to Draft. 

7.	When creating a Generic Team Member, it will be possible to associate the Generic Team Member to a Subcontract line. This is to indicate that desire to staff the Generic Team Member with subcontractor capacity.

8.	Named Team Members can be created directly on a project or when a Booking is made. On a Named Project Team Member, it will be possible to associate to a Subcontract line if the Named Team Member is a Contract Worker. Doing this will drawdown the capacity on a Subcontract line. 

9.	Subcontractor resources will be able to log time, expenses and material usage on projects and project tasks and submit for approval, similar to Employees. When recording time, a contract worker will be able select as Subcontract and Subcontract line. 

10.	Upon approval, time approved by subcontracts will record Project cost actuals based on the purchase price of the Contract worker or the Role they performed on the project.

11.	Vendor Invoices and Vendor invoice line items can be recorded in the system. Vendor invoice lines must be specific to a project and for a transaction class of Time, Expense, Product/Material and Milestone or Fee. Vendor invoice lines can optionally reference a subcontract line. 

12.	System will automatically associate all cost actuals that match the subcontract line and project to the vendor invoice to facilitate 3-way match and verification process. 

13.	Project Manager will be able to review the automatically matched project actuals, remove or add other project cost actuals and complete verification process. 

14.	Completing the verification process on all lines will mark the Vendor Invoice as Ready for Payment. At this stage, vendor invoice and its lines can be transferred to an Accounting or Payables system for processing the payment to the vendor. Previously recorded project costs will be reversed and actual costs from the vendor invoice line will be recorded on the project. 

## Scope of Quantity-based and Work-based Subcontract lines for October 2021 Early Access
In the Early access scope of October 2021, only quantity-based subcontract lines are supported. This means that a subcontract line can be used to purchase Time, Expenses or Materials from a vendor but not a whole body of work. It also means that the quantity being purchased (units of time, expenses, or quantity of materials) on a subcontract line can be used on any project in the system. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
