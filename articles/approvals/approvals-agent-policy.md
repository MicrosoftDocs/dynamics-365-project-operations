---
title: Set up policy documents for the Approvals feature of the Time and Expense Agent (preview)
description: Learn how to set up time, expense, and material policy documents for the Approvals feature of the Time and Expense Agent. 
author: abriccetti
ms.author: abriccetti
ms.date: 05/13/2025
ms.topic: how-to
ms.custom: 
 - bap-template
ms.reviewer: johnmichalak
---

# Set up policy documents for the Approvals feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

The Approvals feature of the Time and Expense Agent uses the text of policy documents to determine how submitted time, expense, and material records should be classified. This article provides information to help you create policy documents. It outlines the information that is available to the agent, recommends a structure for policy documents, and provides links to examples of policy documents for time, expense, and materials.

## Data for the Approvals feature of the Time and Expense Agent

When the Approvals feature of the Time and Expense Agent is triggered, a predefined set of data that is related to the submitted record is passed to the agent. The agent uses this data to classify the record. The agent can perform checks based only on data that is passed to it. If you want to pass data that isn't part of the predefined set, you must customize the agent's trigger flow.

The following tables outline the data that is available to the agent without customization.

### Time entry data

| Name | Description |
|---|---|
| ID | The globally unique identifier (GUID) of the project approval record. |
| Entry type | The type of entry. The possible values are **Time**, **Material**, and **Expense**. |
| Quantity of hours | The amount of submitted time, in hours. |
| Billable hours | The amount of submitted time that is billable, in hours. |
| Cost of time submitted | The total cost of the submitted time. |
| Hourly cost rate | The hourly cost price of the submitted time. |
| Revenue of time submitted | The total sales amount of the billable time. |
| Hourly bill rate | The sales price of the billable time. |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed**, and **Not Applicable**. |
| Not to exceed limit validation detail | Details of the not-to-exceed test. |
| Internal description of the work | The description from the time entry. |
| Customer-facing description of work | External comments from the time entry. |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. |
| Project | The name of the project that time was submitted against. |
| Project task | The name of the project task that time was submitted against. |
| Date logged relative to team member start and end date | The possible values are **Within**, **Falls outside dates**, and **0**. A value of **0** indicates that the person isn't a team member. |
| Submitted by | The resource that submitted the time. |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. |
| Role of the resource | The role that is assigned to the submitter. A value of **0** indicates that no role is assigned. |
| Division of the resources | The organizational unit of the submitter. |
| Relative to the resource assignment period | A value that indicates whether the time entry falls inside the date range that the resource is assigned to the task for. |
| Time submitted against subcontract line | A value that indicates whether the time was submitted against a subcontract line. |
| Time entry type | The type of time entry. The possible values are **Work**, **Overtime**, **Absence**, and **Vacation**. |
| Resource schedule code for slot | The resource schedule code for the slot. The possible values are **Available** and **Unavailable**. |
| Resource schedule subcode for slot | The resource schedule subcode for the slot. The possible values are **Schedulable** and **Holiday**. |
| Logged on working day | A value that indicates whether the time was logged on a working day in the submitter's calendar. The possible values are **True** and **False**. |
| Relative to resources capacity for the day | A value that indicates whether the number of hours that the resource recorded for the date across all time entries exceeds that resource's working hours capacity for that day. |
| Resource Assignment Effort | The total effort on the resource's assignment for the submitted task. |
| Relative to weekly team member effort for this project | The possible values are **Within allocation**, **Violation**, and **0**. A value of **0** indicates that no team member or effort is specified. |

### Expense entry data

| Name | Description |
|---|---|
| ID | The GUID of the project approval record. |
| Entry type | The type of entry. The possible values are **Time**, **Material**, and **Expense**. |
| Quantity of expense submitted | The quantity of the submitted expense. |
| Billable quantity of expense | The quantity of the submitted expense that is billable. |
| Total cost of expense | The total cost of the submitted expense. |
| Per unit cost of expense | The hourly cost price of the submitted expense. |
| Total billable expense amount | The total sales amount of the billable expense. |
| Per unit billing rate of expense | The sales price of the billable expense. |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed** and **Not Applicable**. |
| Not to exceed limit validation detail | Details of the not-to-exceed test. |
| Internal description of the expense | The value of the **Expense purpose** field from the expense entry. |
| Customer-facing description of expense | External comments from the expense entry. |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. |
| Project | The name of the project that time was submitted against. |
| Project task | The name of the project task that time was submitted against. |
| Date logged relative to team member start and end date | The possible values are **Within**, **Falls outside dates**, and **0**. A value of **0** indicates that the person isn't a team member. |
| Submitted by | The resource that submitted the time. |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. |
| Division of the resources | The organizational unit of the submitter. |
| Quantity submitted against subcontract line | A value that indicates whether the expense was submitted against a subcontract line. |
| Does the expense have a receipt | A value that indicates whether there is a receipt for the expense. The possible values are **True** and **False**. |
| Date the expense occurred | The date of the expense entry. |
| Category of expense | The expense category. |
| Whether a receipt is required for this type of expense | A value that specifies whether the expense category requires a receipt. |

### Material entry data

| Name | Description |
|---|---|
| ID | The GUID of the project approval record. |
| Entry type |  The type of entry. The possible values are **Time**, **Material**, and **Expense**. |
| Quantity of material submitted | The quantity of the submitted material. |
| Billable quantity of material | The quantity of the submitted material that is billable. |
| Total cost of material | The total cost of the submitted material. |
| Per unit cost of material | The hourly cost price of the submitted material. |
| Total billable material amount | The total sales amount of the billable material. |
| Per unit billing rate of material | The sales price of the billable material. |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed** and **Not Applicable**. |
| Not to exceed limit validation detail | Details of the not-to-exceed test. |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. |
| Project | The name of the project that material was submitted against. |
| Project task | The name of the project task that material was submitted against. |
| Date logged relative to team member start and end date | The possible values are **Within**, **Falls outside dates**, and **0**. A value of **O** indicates that the person isn't a team member. |
| Submitted by | The resource that submitted the material usage. |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. |
| Division of the resources | The organizational unit of the submitter. |
| Relative to the resource assignment period | A value that indicates whether the expense entry is inside the date range that the resource is assigned to the task for. |
| Quantity submitted against subcontract line | A value that indicates whether the material was submitted against a subcontract line. |
| Name of the existing product in the catalog | The name of the product that was submitted, from the material catalog. |
| Description of the purpose of material usage | The material usage purpose comment from material entry. |
| Type of the product selected | A value that specifies whether the selected product is an existing product or a write-in product. |
| Date the material was procured | The date of material entry. |

## Policy document examples

You can use the following examples of policy documents as a starting point. We recommend that you write a policy document as a numbered list of rules. If a record that is checked violates one or more rules, it's marked as **Needs review**.

- [Time sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocTime.docx)
- [Expense sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocExpense.docx)
- [Material sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocMaterial.docx)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
