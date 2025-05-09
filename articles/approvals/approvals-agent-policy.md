---
title: Set up policy documents for the Approvals feature of the Time and Expense Agent (preview)
description: Learn about how to set up time, material, and expense policy documents for the Approvals feature of the Time and Expense Agent. 
author: abriccetti
ms.author: abriccetti
ms.date: 05/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Set up policy documents for the Approvals feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

The Approvals feature of the Time and Expense Agent makes decisions on how to classify a submitted record based upon the text of the policy document. To help with creating these documents, this article outlines the information available to the agent, recommend policy document structures, and provide examples of policy documents for time, expense, and material.

## Time and Expense Agent Approval's feature data

When the Approvals feature of the Time and Expense Agent is triggered a predetermined set of data related to the submitted record is sent to the agent to help with the classification. The agent can only make checks based on information it was passed. Sending more data about the time/material/expense submission requires customization of the agent's trigger flow. The following charts outline what information is available to the agent without customization. 

### Time entry data

|Name                                                         | Explanation|
|-------------------------------------------------------------|------------|
|ID                                                           |GUID of the Project Approval record|
|Entry type                                                   |Time/Material/Expense|
|Quantity of hours                                            |Quantity of submitted time in hours|
|Billable hours                                               |Quantity of submitted time in hours which is billable|
|Cost of time submitted                                       |Total cost of submitted time|
|Hourly cost rate                                             |Hourly cost price of submitted time|
|Revenue of time submitted                                    |Total sales amount of billable time|
|Hourly bill rate                                             |Sales price of billable time|
|Result of validation against contractual limits              |Status of not to exceed validation (Passed/Failed/Not Applicable)|
|Not to exceed limit validation detail                        |Details of not to exceed test|
|Internal description of the work                             |Description from time entry|
|Customer-facing description of work                          |External comments from time entry|
|Billing type                                                 |Chargeable/NonChargeable/Complimentary/NotAvailable|
|Project                                                      |Name of the project time was submitted against|
|Project task                                                 |Name of the project task time was submitted against|
|Date logged relative to team member start and end date       |Within/Falls outside dates; O if not a team member|
|Submitted by                                                 |Resource which submitted the time|
|Contractor/Employee                                          |Specifies if submitter is an employee or contractor|
|Role of the resource                                         |Role assigned to the submitter, O if no role assigned|
|Division of the resources                                    |Organizational unit of the submitter|
|Relative to the resource assignment period                   |Does the time entry fall inside the dates the resources is assigned to the task|
|Time submitted against subcontract line                      |Was the time submitted against a subcontract line|
|Time entry type                                              |Work/Overtime/Absence/Vacation|
|Resource schedule code for slot                              |Available/Unavailable|
|Resource schedule subcode for slot                           |Schedulable/Holiday|
|Logged on working day                                        |Was the time logged on a working day on the submitter's calendar (true/false)|
|Relative to resources capacity for the day                   |Whether the hours of time across all time entries recorded by this resource for this date exceeds their working hours capacity for the day|
|Resource Assignment Effort                                   |Total effort on the resource's assignment for the submitted task|
|Relative to weekly team member effort for this project       |Within allocation/Violation, O if no team member or effort not specified|

### Expense entry data

|Name                                                         | Explanation|
|-------------------------------------------------------------|------------|
|ID                                                           |GUID of the Project Approval record|
|Entry type                                                   |Time/Material/Expense|
|Quantity of expense submitted                                |Submitted quantity|
|Billable quantity of expense                                 |Quantity of submitted expense which is billable|
|Total cost of expense                                        |Total cost of submitted expense|
|Per unit cost of expense                                     |Hourly cost price of submitted expense|
|Total billable expense amount                                |Total sales amount of billable expense|
|Per unit billing rate of expense                             |Sales price of billable expense|
|Result of validation against contractual limits              |Status of not to exceed validation (Passed/Failed/Not Applicable)|
|Not to exceed limit validation detail                        |Details of not to exceed test|
|Internal description of the expense                          |Expense purpose field from expense entry|
|Customer-facing description of expense                       |External comments from expense entry|
|Billing type                                                 |Chargeable/NonChargeable/Complimentary/NotAvailable|
|Project                                                      |Name of the project time was submitted against|
|Project task                                                 |Name of the project task time was submitted against|
|Date logged relative to team member start and end date       |Within/Falls outside dates; O if not a team member|
|Submitted by                                                 |Resource which submitted the time|
|Contractor/Employee                                          |Specifies if submitter is an employee or contractor|
|Division of the resources                                    |Organizational unit of the submitter|
|Quantity submitted against subcontract line                  |Was the expense submitted against a subcontract line|
|Does the expense have a receipt                              |True/False|
|Date the expense occurred                                    |Date of expense entry|
|Category of expense                                          |Expense category|
|Whether a receipt is required for this type of expense       |The expense category does/does not mandate a receipt|

### Material entry data

|Name                                                         | Explanation|
|-------------------------------------------------------------|------------|
|ID                                                           |GUID of the Project Approval record|
|Entry type                                                   |Time/Material/Expense|
|Quantity of material submitted                               |Submitted quantity|
|Billable quantity of material                                |Quantity of submitted material which is billable|
|Total cost of material                                       |Total cost of submitted material|
|Per unit cost of material                                    |Hourly cost price of submitted material|
|Total billable material amount                               |Total sales amount of billable material|
|Per unit billing rate of material                            |Sales price of billable material|
|Result of validation against contractual limits              |Status of not to exceed validation (Passed/Failed/Not Applicable)|
|Not to exceed limit validation detail                        |Details of not to exceed test|
|Billing type                                                 |Chargeable/NonChargeable/Complimentary/NotAvailable|
|Project                                                      |Name of the project material was submitted against|
|Project task                                                 |Name of the project task material was submitted against|
|Date logged relative to team member start and end date       |Within/Falls outside dates; O if not a team member|
|Submitted by                                                 |Resource which submitted the material usage|
|Contractor/Employee                                          |Specifies if submitter is an employee or contractor|
|Division of the resources                                    |Organizational unit of the submitter|
|Relative to the resource assignment period                   |Does the expense entry fall inside the dates the resources is assigned to the task|
|Quantity submitted against subcontract line                  |Was the material submitted against a subcontract line|
|Name of the existing product in the catalog                  |Name of the product which was submitted from material catalog|
|Description of the purpose of material usage                 |Material usage purpose comment from material entry|
|Type of the product selected                                 |Existing or write-in|
|Date the material was procured                               |Date of material entry|

## Policy Document Examples

The following examples are sample policy documents that can be used as a starting point. It's recommended you write a policy document as a numbered list of rules, which if the record being checked violates one or more rules it's marked as needs review.

[Time Sample Policy Document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocTime.docx)

[Expense Sample Policy Document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocExpense.docx)

[Material Sample Policy Document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocMaterial.docx)

[!INCLUDE[footer-include](../includes/footer-banner.md)]



