---
title: Set up policy documents for the Approvals Agent (preview)
description: Learn how to set up time, expense, and material policy documents for the Approvals feature of the Time and Expense Agent. 
author: abriccetti
ms.author: abriccetti
ms.date: 07/21/2026
ms.topic: how-to
ms.custom: 
 - bap-template
ms.reviewer: johnmichalak
---

# Set up policy documents for the Approvals Agent (preview)

> [!IMPORTANT]
> - This is a production-ready preview feature.
> - Production-ready previews are subject to [supplemental terms of use](https://www.microsoft.com/en-us/business-applications/legal/supp-powerplatform-preview/).

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

***Applies To:** Project Operations Integrated with ERP, Project Operations Core*

The Approvals Agent uses the text of policy documents to determine how to classify submitted time, expense, and material records. This article provides information to help you create policy documents. It outlines the information that the agent can access, recommends a structure for policy documents, and provides links to examples of policy documents for time, expense, and materials.

## Data for the Approvals Agent

When you trigger the Approvals Agent, it receives a predefined set of data related to the submitted record. The agent uses this data to classify the record. The agent can only perform checks based on the data it receives. If you want to pass data that isn't part of the predefined set, you must customize the agent's trigger flow.

The following tables outline the data that is available to the agent without customization. Learn more about customizing this data in [Customize data sent to the Approvals Agent](approvals-agent-customization.md).

Not all data signals are present on every record. Some signals are only included when specific criteria are met (for example, budget data only appears when the project has an active approved budget). The **Conditions for inclusion** column in each table indicates whether a signal is always included or describes the specific conditions that must be met for it to appear.

### Time entry data

| Name | Description | Example output | Conditions for inclusion |
| --- | --- | --- | --- |
| ID | The globally unique identifier (GUID) of the project approval record. | `a1b2c3d4-5678-90ab-cdef-1234567890ab` | Always |
| Entry type | The type of entry. The possible values are **Time**, **Material**, and **Expense**. | `Time` | Always |
| Quantity of hours | The amount of submitted time, in hours. | `8 hours` | Always |
| Billable hours | The amount of submitted time that is billable, in hours. | `6.5 hours` | Always |
| Cost of time submitted | The total cost of the submitted time. | `$480.00` | Always |
| Hourly cost rate | The hourly cost price of the submitted time. | `$60.00` | Always |
| Revenue of time submitted | The total sales amount of the billable time. | `$650.00` | Always |
| Hourly bill rate | The sales price of the billable time. | `$100.00` | Always |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed**, and **Not Applicable**. | `Pass` | Always |
| Not to exceed limit validation detail | Details of the not-to-exceed test. | `Amount exceeds contract line limit` | Always |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. | `Chargeable` | Always |
| Internal description of the work | Internal comments from the time entry. | `Pair programmed with Sarah` | Only when internal comments are non-empty. |
| Customer-facing description of work | External comments from the time entry. | `Implemented login flow` | Only when external comments are non-empty. |
| Project | The name of the project that time was submitted against. | `Contoso ERP Implementation` | Only when the approval is linked to a project. |
| Project task | The name of the project task that time was submitted against. If no task is linked, the value is **Missing project task**. | `Design Phase` | Always |
| Date logged relative to team member start and end date | A value that indicates whether the entry date falls within the team member's start and end dates on the project. The possible values are **Within** and **Falls outside dates**. | `Within` | Only when the resource is a project team member with start and end dates set. |
| Submitted by | The name of the resource that submitted the time. | `John Smith` | Always |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. | `Employee` | Only when the bookable resource has a worker type set. |
| Role of the resource | The role that is assigned to the submitter. | `Senior Developer` | Always |
| Division of the worker | The organizational unit of the submitter. | `US East Engineering` | Only when the resource has an organizational unit assigned. |
| Relative to the resource assignment period | A value that indicates whether the time entry falls inside the date range that the resource is assigned to the task for. The possible values are **Within assignment period** and **Outside assignment period**. | `Within assignment period` | Only when a resource assignment exists for the task with start and end dates set. |
| Time submitted against subcontract line | A value that indicates whether the time submitted exceeds the subcontract line's available capacity. The possible values are **Violation: Submitted quantity exceeds available capacity**, **Within available capacity**, and **Not Applicable**. | `Not Applicable` | Always (shows **Not Applicable** when no subcontract line exists). |
| Subcontract line name | The name of the associated subcontract line. | `SC-001: Development Services` | Only when the linked time entry has a subcontract line. |
| Time entry type | The type of time entry. The possible values are **Work**, **Overtime**, **Absence**, and **Vacation**. | `Work` | Always |
| Logged on working day | A value that indicates whether the time was logged on a working day in the submitter's calendar. The possible values are **True** and **False**. | `True` | Always |
| Relative to resource's capacity for the day | A value that indicates whether the number of hours that the resource recorded for the date across all time entries exceeds that resource's working hours capacity for that day. The possible values are **Violation** and **Within allocation**. | `Within allocation` | Always |
| ResourceAssignmentEffort | The total planned effort (in hours) allocated to the resource assignment on the task. | `40.0` | Only when a resource assignment exists for the task with an effort value set, and the resource has logged time against the task. |
| Allocated effort for resource assignment | A value that indicates whether the total time logged against the task exceeds the planned resource assignment effort. The possible values are **Violation** and **Within allocation**. | `Within allocation` | Only when a resource assignment exists for the task with an effort value set, and the resource has logged time against the task. |
| Team member effort | The weekly effort (in hours) allocated to the team member on this project. | `40.0` | Only when the resource is a project team member with an effort value set, and the resource has logged time on the project. |
| Relative to weekly team member effort for this project | A value that indicates whether the total time logged on the project exceeds the team member's weekly effort allocation. The possible values are **Violation** and **Within allocation**. | `Within allocation` | Only when the resource is a project team member with an effort value set, and the resource has logged time on the project. |
| Category of work | The transaction category classifying the type of work. | `Development` | Only when a transaction category is set on the approval. |
| Cost budget for amount | A value that indicates whether approving this entry would exceed the cost budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has an amount set. |
| Cost budget for quantity | A value that indicates whether approving this entry would exceed the cost budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has a quantity set. |
| Sales budget for amount | A value that indicates whether approving this entry would exceed the sales budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has an amount set. |
| Sales budget for quantity | A value that indicates whether approving this entry would exceed the sales budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has a quantity set. |

### Expense entry data

| Name | Description | Example output | Conditions for inclusion |
| --- | --- | --- | --- |
| ID | The GUID of the project approval record. | `a1b2c3d4-5678-90ab-cdef-1234567890ab` | Always |
| Entry type | The type of entry. The possible values are **Time**, **Material**, and **Expense**. | `Expense` | Always |
| Quantity of expense submitted | The quantity of the submitted expense. | `1` | Always |
| Billable quantity of expense | The quantity of the submitted expense that is billable. | `1` | Always |
| Total cost of expense submitted | The total cost of the submitted expense. | `$350.00` | Always |
| Per unit cost of expense | The per-unit cost price of the submitted expense. | `$350.00` | Always |
| Total billable expense amount | The total sales amount of the billable expense. | `$350.00` | Always |
| Per unit billing rate of expense | The per-unit sales price of the billable expense. | `$350.00` | Always |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed**, and **Not Applicable**. | `Pass` | Always |
| Not to exceed limit validation detail | Details of the not-to-exceed test. | `Amount exceeds contract line limit` | Always |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. | `Chargeable` | Always |
| Internal description of the expense | Internal comments from the expense entry. | `Booked via corporate travel portal` | Only when internal comments are non-empty. |
| Customer-facing description of the expense | External comments from the expense entry. | `Client site travel` | Only when external comments are non-empty. |
| Project | The name of the project that the expense was submitted against. | `Contoso ERP Implementation` | Only when the approval is linked to a project. |
| Project task | The name of the project task that the expense was submitted against. If no task is linked, the value is **Missing project task**. | `Design Phase` | Always |
| Date logged relative to team member start and end date | A value that indicates whether the entry date falls within the team member's start and end dates on the project. The possible values are **Within** and **Falls outside dates**. | `Within` | Only when the resource is a project team member with start and end dates set. |
| Submitted by | The name of the resource that submitted the expense. | `John Smith` | Always |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. | `Employee` | Only when the bookable resource has a worker type set. |
| Role of the resource | The role that is assigned to the submitter. | `Senior Developer` | Only when the resource has a role (bookable resource category) assigned. |
| Division of the worker | The organizational unit of the submitter. | `US East Engineering` | Only when the resource has an organizational unit assigned. |
| Quantity submitted against subcontract line | A value that indicates whether the expense submitted exceeds the subcontract line's available capacity. The possible values are **Violation: Submitted quantity exceeds available capacity**, **Within available capacity**, and **Not Applicable**. | `Not Applicable` | Always (shows **Not Applicable** when no subcontract line exists). |
| Subcontract line name | The name of the associated subcontract line. | `SC-001: Development Services` | Only when the linked expense entry has a subcontract line. |
| Does the expense have a receipt? | A value that indicates whether there is a receipt for the expense. The possible values are **True** and **False**. | `True` | Always |
| Description of the purpose of the expense | The name/purpose description from the expense entry. | `Flight to Seattle for client meeting` | Only when the expense entity has a name set. |
| Customer facing description of the expense | The external description from the expense entity. | `On-site consultation travel` | Only when the expense entity has an external description set. |
| Date the expense occurred | The actual transaction date of the expense. | `Friday, June 12, 2026` | Always |
| Category of expense | The expense category name. | `Airfare` | Always |
| Whether a receipt is required for this type of expense | A validation message about receipt requirements for this category. The possible values are **Expense has the required receipt**, **Missing required receipt**, and **The expense category does not mandate a receipt**. | `Expense has the required receipt` | Always |
| Category of expense (type) | The expense type from the category definition. | `Travel` | Only when the expense category has an expense type set. |
| Description of the attached receipt on this expense | A description of the receipt contents attached to the expense. | `Delta Airlines receipt, SEA-SFO, $347.50` | Only when the expense has an associated receipt with a description. |
| Date of expense entry | The date the expense was logged in the system. | `Monday, June 15, 2026` | Always |
| Cost budget for amount | A value that indicates whether approving this entry would exceed the cost budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has an amount set. |
| Cost budget for quantity | A value that indicates whether approving this entry would exceed the cost budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has a quantity set. |
| Sales budget for amount | A value that indicates whether approving this entry would exceed the sales budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has an amount set. |
| Sales budget for quantity | A value that indicates whether approving this entry would exceed the sales budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has a quantity set. |

### Material entry data

| Name | Description | Example output | Conditions for inclusion |
| --- | --- | --- | --- |
| ID | The GUID of the project approval record. | `a1b2c3d4-5678-90ab-cdef-1234567890ab` | Always |
| Entry type | The type of entry. The possible values are **Time**, **Material**, and **Expense**. | `Material` | Always |
| Quantity of material submitted | The quantity of the submitted material. | `5` | Always |
| Billable quantity of material | The quantity of the submitted material that is billable. | `5` | Always |
| Total cost of the submitted material | The total cost of the submitted material. | `$250.00` | Always |
| Per unit cost of material | The per-unit cost price of the submitted material. | `$50.00` | Always |
| Total billable amount for the material used | The total sales amount of the billable material. | `$375.00` | Always |
| Per unit billing rate of the material | The per-unit sales price of the billable material. | `$75.00` | Always |
| Result of validation against contractual limits | The status of not-to-exceed validation. The possible values are **Passed**, **Failed**, and **Not Applicable**. | `Pass` | Always |
| Not to exceed limit validation detail | Details of the not-to-exceed test. | `Amount exceeds contract line limit` | Always |
| Billing type | The billing type. The possible values are **Chargeable**, **NonChargeable**, **Complimentary**, and **NotAvailable**. | `Chargeable` | Always |
| Internal description of the material usage | Internal comments from the material entry. | `Ordered from preferred vendor` | Only when internal comments are non-empty. |
| Customer-facing description of material usage | External comments from the material entry. | `Cables for server room` | Only when external comments are non-empty. |
| Project | The name of the project that material was submitted against. | `Contoso ERP Implementation` | Only when the approval is linked to a project. |
| Project task | The name of the project task that material was submitted against. If no task is linked, the value is **Missing project task**. | `Design Phase` | Always |
| Date logged relative to team member start and end date | A value that indicates whether the entry date falls within the team member's start and end dates on the project. The possible values are **Within** and **Falls outside dates**. | `Within` | Only when the resource is a project team member with start and end dates set. |
| Submitted by | The name of the resource that submitted the material usage. | `John Smith` | Always |
| Contractor/Employee | A value that specifies whether the submitter is an employee or a contractor. | `Employee` | Only when the bookable resource has a worker type set. |
| Role of the resource | The role that is assigned to the submitter. | `Senior Developer` | Only when the resource has a role (bookable resource category) assigned. |
| Division of the worker | The organizational unit of the submitter. | `US East Engineering` | Only when the resource has an organizational unit assigned. |
| Quantity submitted against subcontract line | A value that indicates whether the material submitted exceeds the subcontract line's available capacity. The possible values are **Violation: Submitted quantity exceeds available capacity**, **Within available capacity**, and **Not Applicable**. | `Not Applicable` | Always (shows **Not Applicable** when no subcontract line exists). |
| Subcontract line name | The name of the associated subcontract line. | `SC-001: Development Services` | Only when the linked material entry has a subcontract line. |
| Name of the existing product in the catalog | The name of the product from the product catalog. | `Cat6 Ethernet Cable 10ft` | Only when the material usage log has a product display name set. |
| Type of the product selected | A value that specifies whether the selected product is an existing product or a write-in product. The possible values are **Existing** and **Write-in**. | `Existing` | Always (defaults to **Existing** if not overridden). |
| Write In Product Description | The description for a manually entered (write-in) product. | `Custom mounting bracket` | Always (from material usage log attribute; may be empty). |
| Description of the purpose of material usage | The material usage purpose comment from the material entry. | `Network infrastructure upgrade` | Always (shows **Not specified** if no purpose is provided). |
| Date the material was procured | The actual transaction date when the material was procured. | `Wednesday, June 10, 2026` | Always |
| Date of material entry | The date the material usage was logged in the system. | `Monday, June 15, 2026` | Always |
| Category of material | The transaction category classifying the material. | `Hardware` | Only when a transaction category is set on the approval. |
| Cost budget for amount | A value that indicates whether approving this entry would exceed the cost budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has an amount set. |
| Cost budget for quantity | A value that indicates whether approving this entry would exceed the cost budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching cost budget line that has a quantity set. |
| Sales budget for amount | A value that indicates whether approving this entry would exceed the sales budget line amount. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has an amount set. |
| Sales budget for quantity | A value that indicates whether approving this entry would exceed the sales budget line quantity. The possible values are **Violation** and **Within Budget**. | `Within Budget` | Only when the project has an active approved budget with a matching sales budget line that has a quantity set. |

## Policy document examples

Use the following examples of policy documents as a starting point. Write a policy document as a numbered list of rules. If a record that the system checks violates one or more rules, the system marks it as **Needs review**.

- [Time sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocTime.docx)
- [Expense sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocExpense.docx)
- [Material sample policy document](https://download.microsoft.com/download/fe7df267-f397-46bd-ae8a-eaeb5ab6f8b0/SamplePolicyDocMaterial.docx)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
