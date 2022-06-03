---
title: Work with project–based contract lines
description:  This article provides information about project–based contract lines.
author: rumant
ms.date: 10/28/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Work with project–based contract lines

Project-based contract lines in Dynamics 365 Project Operations are designed to hold the estimate and billing agreements for specific components of project work on an engagement. The structure of a project–based contract line is extended for project estimates and billing scenarios with the following concepts:

- Billing method
- Project and task mapping
- Included transaction classes
- Not-to-exceed limit
- Chargeability setup
- Estimates using contract line details
- Contract line customers

The following fields are included on the **General** tab of project–based contract lines. These fields help to set up the basis for a detailed, ground–up estimate and the billing arrangements for project–based work.

| Field | Description | Downstream impact |
| --- | --- | --- |
| **Name** | The name of the contract line that identifies the discrete component of the contract that is being estimated. For a project contract created from a quote, this value is copied from a corresponding value of the project-based quote line. | This field value is copied to the project invoice line that is created from this contract line when the invoice is created. |
| **Billing Method** | On a project contract created from a quote, this value is copied from the corresponding field on the quote line. This is an option set that represents the two main contracting models supported by Project Operations:</br>- **Fixed Price**</br>- **Time and Material** | Based on the billing method of the referenced contract line, the actual transaction will be processed. If the contract line referenced by the actual has a time and material billing method, a cost and an unbilled sales actual record are created. If the contract line referenced by the actual has a fixed price billing method, only a cost actual is created. |
| **Project** | Use this field to identify the project that will be used to deliver the work on this engagement. | The value in this field is used in conjunction with **Included Tasks** and **Included Transaction Classes** fields to resolve the contract line reference on an actual or an estimate line record. |
| **Include Time** | A flag indicates if time transactions or labor costs on the selected project are included on this contract line. A **No** value indicates that the time transactions or labor costs will not be included on this contract line. A **Yes** value indicates that they will. | This field value is used in conjunction with project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Expense** | A flag indicates if expense costs on the selected project will be included on this contract line. A **No** value indicates that the expense cost will not be included on this contract line. A **Yes** value indicates that it will. | This field value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Fee** | A flag indicates if fees on the selected project will be included on this contract line. A **No** value indicates that the fees will not be included on this contract line. A **Yes** value indicates that they will. | This field value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Contracted Amount** | On a fixed price contract line, this is the agreed-on value that will be invoiced to the customer for all the work components associated with this contract line. On a time and material contract line, this amount is an estimated value of what will be invoiced to the customer for all the work components associated to this contract line. On a project contract that is created from a quote, this value is copied from the corresponding field on the quote line. When a project–based contract line has line details, this field is locked for editing and is summarized from the amount on the contract line details. | When the contract line has line details, this value can be modified by changing the amounts on the line details. On a fixed price contract line, this value is used to generate the amount before tax on periodic billing milestones. |
| **Estimated Tax** | The user can edit this field to input the estimated tax amount on the contract line. When a project–based contract line has line details, this field is locked for editing and is summarized from the tax amount on the contract line details. | When the contract line has line details, this value can be modified by changing the tax amounts on the line details. On a fixed price contract line, this value is used to generate tax on periodic billing milestones. |
| **Contracted Amount after Tax** | The contract line amount after tax. This field is read-only and is calculated as **Contracted Amount + Tax**. | On a fixed price contract line, this value is used to generate periodic billing milestones. |
| **Not-to-Exceed Limit** | The user can edit this field and it is only available on project-based contract lines that have a time and material billing method. | The user can edit this field. When a time or expense actual references this contract line for time and material, the amount on the actual is evaluated against the not-to-exceed limit on this contract line after accounting for the already spent and committed amounts. |
| **Customer Budget** | This field is editable and is copied from the corresponding field on the quote line, if the contract was created from a quote. | This field is only used for information and does not have any downstream significance. |

## Validation rule for the options on the General tab of project-based contract lines

Rule: A project and a certain transaction class can only be included on one project-based contract line in a contract.

| Contract | Contract line | Project | Include time | Include expense | Include fee | Valid/not valid | Reason                                                                                                                                                                                                  |
|----------|---------------|---------|--------------|-----------------|-------------|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| C1       | CL1           | P1      | Yes          | Yes             | Yes         | Not valid       | Violates the rule. Time,   expense, and fees on project P1 are included on both contract lines, CL1 and   CL2.                                                                                       |
| C1       | CL2           | P1      | Yes          | Yes             | Yes         | Not valid       | Violates the rule. Time,   expense, and fees on project P1 are included on both contract lines, CL1 and   CL2.                                                                                       |
| C1       | CL1           | P1      | Yes          | No              | Yes         | Not valid       | Violates the rule. Time and   fees on project P1 are included on both contract lines, CL1 and CL2.                                                                                                   |
| C1       | CL2           | P1      | Yes          | Yes             | Yes         | Not valid       | Violates the rule. Time and   fees on project P1 are included on both contract lines, CL1 and CL2.                                                                                                   |
| C1       | CL1           | P1      | Yes          | No              | Yes         | Valid           | Time and fees on project P1 are   included on the CL1. Expense on project P1 is included on CL2. </br>   There is no overlap in what is being included on each contract line and is   therefore valid.  |
| C1       | CL2           | P1      | No           | Yes             | No          | Valid           | Time and fees on project P1 are   included on the CL1. Expense on project P1 is included on CL2. </br>   There is no overlap in what is being included on each contract line and is   therefore valid.  |
| C1       | CL1           | P1      | Yes          | Yes             | Yes         | Not valid       | Violates the rule. Time,   expense, and fees on project P1 are included on the lines of two contracts.                                                                                               |
| CL2      | CL2           | P1      | Yes          | Yes             | Yes         | Not valid       | Violates the rule. Time,   expense, and fees on project P1 are included on the lines of two contracts.                                                                                               |


[!INCLUDE[footer-include](../includes/footer-banner.md)]