---
title: Managing Subcontracts in Project Operations
description: This topic provides overview about end-to-end management of Subcontracts in Project Operations.
author: rumant
ms.date: 07/28/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Managing Subcontracts in Project Operations

_**Applies To:** Lite deployment - deal to proforma invoicing_

Subcontracting in Project Operations supports the business process flow as below:

> ![Subcontracting Process Flow](./media/Subcontracting Process Flow.png)
  
Below is a step-by-step description of Subcontracting process in Project Operations:
1.	Project Manager creates a subcontract with a Vendor. Price lists on the subcontract are defaulted from the Price Lists attached to the Vendor record. Vendor is an Account with Relationship type as Vendor or Supplier.
2.	Project Manager can itemize all the purchases as line items on the Subcontract. Subcontract Lines can be for Time, Expense or Products. This is determined by the Transaction class selected on the Subcontract line.
3.	Vendor Account Manager and the Project Manager can iterate over the subcontract. Pricing can be adjusted in the Purchase Price List(s) attached to the Subcontract. 
4.	At this stage or later in the process, Vendor Account Manager associate contacts to each Subcontract line, if the Subcontract line is for Time. This is to indicate to the PM who will be working on subcontract. When associating a Contact to the Subcontract line, the system will automatically create a Bookable Resource from a Contact if it does not exist already. 
5.	Billing Method on the Subcontract line can be Fixed Price or T&M. For Fixed Price Subcontract lines, there is the ability to setup a Milestone based invoice schedule. 
The below is functionality not yet released for Early Access of 2021 Release Wave 2 and will be released in updates post the GA of 2021 Release Wave 2.

6.	Once the subcontract is setup, it should be confirmed. Confirmed subcontracts cannot be edited but should changes occur, a Subcontract can be ‘reopened for edits’ that moves the status from Confirmed back to Draft. 
7.	When creating a Generic Team Member, it will be possible to associate the Generic Team Member to a Subcontract line. This is to indicate that desire to staff the Generic Team Member with subcontractor capacity.
8.	Named Team Members can be created directly on a project or when a Booking is made. On a Named Project Team Member, it will be possible to associate to a Subcontract line if the Named Team Member is a Contract Worker. Doing this will drawdown the capacity on a Subcontract line. 
9.	Subcontractor resources will be able to log time, expenses and material usage on projects and project tasks and submit for approval, similar to Employees. When recording time, a contract worker will be able select as Subcontract and Subcontract line. 
10.	Upon approval, time approved by subcontracts will record Project cost actuals based on the purchase price of the Contract worker or the Role they performed on the project.
11.	Vendor Invoices and Vendor invoice line items can be recorded in the system. Vendor invoice lines must be specific to a project and for a transaction class of Time, Expense, Product/Material and Milestone or Fee. Vendor invoice lines can optionally reference a subcontract line. 
12.	System will automatically associate all cost actuals that match the subcontract line and project to the vendor invoice to facilitate 3-way match and verification process. 
13.	Project Manager will be able to review the automatically matched project actuals, remove or add other project cost actuals and complete verification process. 
14.	Completing the verification process on all lines will mark the Vendor Invoice as Ready for Payment. At this stage, vendor invoice and its lines can be transferred to an Accounting or Payables system for processing the payment to the vendor. Previously recorded project costs will be reversed and actual costs from the vendor invoice line will be recorded on the project. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

