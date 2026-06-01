---
title: Project contract lines overview
description:  This article provides information about working with project contract lines in Project Operations.
author: mukumarm
ms.date: 02/26/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Project contract lines overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Project-based contract lines in Dynamics 365 Project Operations hold the estimate and billing agreements for specific components of project work on an engagement. The structure of a project–based contract line extends for project estimates and billing scenarios with the following concepts:

- Billing method
- Project and task mapping
- Included transaction classes
- Not-to-exceed limit
- Chargeability setup
- Estimates using contract line details
- Contract line customers

The following table describes the fields on the **General** tab of project–based contract lines that help set up the basis for a detailed, ground–up estimate and billing arrangements for project–based work.

| Field | Description | Downstream impact |
| --- | --- | --- |
| **Name** | Name of the contract line. This field identifies the discrete component of the contract that you're estimating. For a project contract created from a quote, the system copies this value from a corresponding value of the project-based quote line. | The name is copied over to the project invoice line that is created from this contract line when the invoice is created. |
| **Billing Method** | <p>On a project contract created from a quote, the system copies this value from the corresponding field on the quote line. This option set represents the two main contracting models supported by Project Operations:</p><ul><li>**Fixed Price**</li><li>**Time and Material**</li></ul> | Based on the billing method of the referenced contract line, the system processes the actual transaction. If the contract line referenced by the actual has a time and material billing method, the system creates cost and unbilled sales actual records. If the contract line referenced by the actual has a fixed price billing method, the system creates only a cost actual. |
| **Invoice Schedule Type** | <p>On a project contract created from a quote, the system copies this value from the corresponding field on the quote line. This option set represents the two invoice schedule types for the **Fixed Price** contracting model supported by Project Operations:</p><ul><li>**Completed Milestones**</li><li>**Progress-based**</li></ul> | The invoice schedule type is relevant for the fixed price billing method in **Core deployment** and **Project Operations Integrated with ERP**. If you set the invoice schedule type to **Progress-based**, you can bill milestones based on the progress percentage. If you set it to **Completed Milestones**, you can bill milestones only when they're fully completed. **Completed Milestones** is the default value. To use the progress-based billing feature, use the parameter page to ensure that **Progress based billing** is enabled. |
| **Project** | Use this field to identify the project that delivers the work on this engagement. | This value is used with **Included Tasks** and **Included Transaction Classes** to resolve the contract line reference on an actual or estimate line record. |
| **Included Tasks** | <p>Indicates if this contract line includes all project tasks for the selected project or only a subset of the tasks. This option set has the following possible values:</p><ul><li>**All Project Tasks**</li><li>**Selected Project Tasks Only**</li></ul><p>A blank value in this field is equal to selecting **All Project Tasks**.</p> | If you select **Selected Tasks Only**, you can select specific tasks and associate them to this contract line on the **Task Billing Setup** tab on the **Project** page. The value is used with **Project** and **Included Transaction** classes to resolve the contract line reference on an actual or an estimate line record. |
| **Include Time** | A **Yes**/**No** value indicates if time transactions or labor costs on the selected project are included on this contract line. A **No** value indicates that the time transactions or labor cost isn't included on this contract line. A **Yes** value indicates that they're included. | This value is used with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Expense** | A **Yes**/**No** value indicates if expense costs on the selected project are included on this contract line. A **No** value indicates that the expense cost isn't included on this contract line. A **Yes** value indicates that it's included. | This value is used with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Materials** | A **Yes**/**No** value indicates if material costs on the selected project are included on this contract line. A **No** value indicates that the material costs aren't included on this contract line. A **Yes** value indicates that it's included. | This value is used with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Fee** | A **Yes**/**No** value indicates if fees on the selected project are included on this contract line. A **No** value indicates that the fees aren't included on this contract line. A **Yes** value indicates that they're included. | This value is used with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Contracted Amount** | On a fixed price contract line, this amount is the agreed-on value that you invoice to the customer for all the work components associated to this contract line. On a time and material contract line, this amount is an estimated value of what you invoice to the customer for all the work components associated to this contract line. On a project contract that you create from a quote, the system copies this value from the corresponding field on the quote line. When a project–based contract line has line details, the system locks this field for editing and summarizes it from the amount on the contract line details. | When the contract line has line details, you can modify this value by changing the amounts on the line details. On a fixed price contract line, the system uses this value to generate the amount before tax on periodic billing milestones. |
| **Estimated Tax** | Edit this field to input the estimated tax amount on the contract line. When a project–based contract line has line details, the system locks this field for editing and summarizes it from the tax amount on the contract line details. | When the contract line has line details, you can modify this value by changing the tax amounts on the line details. On a fixed price contract line, the system uses this value to generate the tax on periodic billing milestones. |
| **Contracted Amount after Tax** | The contract line amount after tax. This field is read only and is calculated as **Contracted Amount + Tax**. | On a fixed price contract line, the system uses this value to generate periodic billing milestones. |
| **Not-to-Exceed Limit** | Edit this field. It's only available on project-based contract lines that have the billing method set as time and material. | Edit this field. When an actual for time and material references this contract line for time and material, the system evaluates the amount on the actual against the not-to-exceed limit on the contract line. This evaluation is completed after  the already spent and committed amounts are accounted for. |
| **Customer Budget** | Edit this field. If you create the contract from a quote, the system copies this value from the corresponding field on the quote line. | This field is only used for information and doesn't have any downstream significance. |

## Validation rules for the options on the General tab of project-based contract lines

Rule 1: If you leave the **Included Tasks** field blank or set it to **All Project Tasks**, you include all tasks of the project on the contract line.

Rule 2: If you leave the **Included Tasks** field blank or explicitly set it to **All Project Tasks**, you can include a project and a certain transaction class on only one project-based contract line of a contract.

Rule 3: If you set the **Included Tasks** field to **Selected Project Tasks Only**, you can include a project and a certain transaction class on multiple project-based contract lines of a contract.

| Contract | Contract line | Project | Included tasks | Include Time | Include Expense | Include Materials | Include Fee | Valid/Not valid | Reason |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| C1 | CL1 | P1 | Blank | Yes | Yes | Yes | Yes | Not valid | Violation of Rule #2. Time, Expense, Materials, and Fees on P1 project are included on both Contract lines CL1 and CL2. |
| C1 | CL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | |
| C1 | CL1 | P1 | Blank | Yes | No | Yes | Yes | Not valid | Violation of Rule #2. Time, Materials, and Fees on P1 project are included on both Contract lines CL1 and CL2. |
| C1 | CL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | |
| C1 | CL1 | P1 | Blank | Yes | No | Yes | Yes | Valid | Time, Materials, and Fees on P1 project are included on CL1. Expense on P1 project is included on CL2. No overlap in what is being included on each Contract line and therefore valid. |
| C1 | CL2 | P1 | Blank | No | Yes | No | No | | |
| | | | | | | | | | |
| C1 | CL1 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | Not valid | Violation of Rule #2. C1 includes Time, Materials, Expenses, and Fees on a subset of tasks on project P1. CL2 includes Time, Materials, Expenses, and Fees for the whole project P1 and therefore overlaps with what is included on C1. |
| C1 | CL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | |
| C1 | CL1 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | Valid | Per Rule #3. C1 includes Time, Expenses, Materials, and Fees on a subset of tasks on project P1. CL2 includes Time, Expenses, Materials, and Fees for a subset of tasks on project P1. The only other validation is around the subset of tasks on CL1 is different from the subset of tasks on CL2 to ensure that there are no overlaps there. The system does this validation when you associate tasks. |
| C1 | CL2 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
