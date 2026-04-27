---
title: Project quote lines overview 
description: This article provides information about using project-based quote lines for project work.
author: poojafandan
ms.date: 02/26/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan

---

# Project quote lines overview 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

Project-based quote lines help you estimate the project work on an engagement. The structure of a project-based quote line extends for project estimates with the following concepts:

- Billing method
- Project and task mapping
- Included transaction classes
- Not-to-exceed limit
- Chargeability setup
- Estimation using quote line details
- Quote line customers

The following table provides information about the fields on the **General** tab of project-based quote line. These fields help set up the basis for a detailed, ground-up estimation for project work.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Name | The name of quote line that helps you to identify the discrete component of the quote that you're estimating. | Copied to the project contract line that is created from this quote line when the quote is won. |
| Billing Method | On a quote created from an opportunity, this value is copied from the corresponding field on the opportunity line. This field includes the two main contracting models supported by Dynamics 365 Project Operations:</br>- Fixed price</br>- Time and material.| This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Project | Use this optional field to identify the project that delivers the work on this engagement. When you map a project to a quote line, it helps with setting up chargeable tasks and also with bringing in a project-based estimate to the quote line as quote line details. When you don't map a project to a project-based quote line, you should create the estimate manually by creating each quote line detail. | This value is copied to the project contract line that is created from this quote line when the quote is won.|
| Included Tasks | Indicates if this quote line is used for all or some of the project tasks for the selected project. This field has the following possible values:</br>- All project tasks</br>- Selected project tasks only</br>A blank value in this field is equivalent to the **All project tasks** option. | When you select **Selected project tasks only** on the project page, the **Task billing setup** tab allows you to select specific tasks to associate them to this quote line. This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Time | A **Yes**/**No** value indicates if time transactions or labor costs on the selected project are included in the estimate on this quote line. A **No** value indicates that the time transactions or labor cost aren't included in the estimate on this quote line. A **Yes** value indicates that the time transactions or labor cost are included in the estimate on this quote line. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Expense | A **Yes**/**No** value indicates if expense costs on the selected project are included in the estimate on this quote line. A **No** value indicates that the expense cost isn't included in the estimate on this quote line. A **Yes** value indicates that the expense cost is included in the estimate on this quote line. | This value is copied over to the project contract line that is created from this quote line when the quote is won. |
| Include Material | A **Yes**/**No** value indicates if material costs on the selected project are included in the estimate on this quote line. A **No** value indicates that the material costs aren't included in the estimate on this quote line. A **Yes** value indicates that the material costs are included in the estimate on this quote line. | This value is copied over to the project contract line that is created from this quote line when the quote is won. |
| Include Fee | A **Yes**/**No** value indicates if fees on the selected project are included in the estimate on this quote line. A **No** value indicates that the fees aren't included in the estimate on this quote line. A **Yes** value indicates that the fees are included in the estimate on this quote line. | This value is copied to the Project contract line that is created from this quote line when the quote is won. |
| Quoted Amount | This amount is quoted to the customer for all the work forecasted on this project-based quote line. On a quote created from an opportunity, this value is copied from the **Customer Budget** field on the opportunity line. When the project-based quote line has line details, this field is locked for editing and is summarized from the amount on the quote line details. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Estimated Tax | This is an editable field for the user to add the estimated tax amount on the quote line. When a project-based quote line has line details, this field is locked for editing and is summarized from the tax amount on the quote line details. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Quoted Amount after Tax | This field is the quote line amount after tax and is read-only. The amount in this field is calculated as *Quoted Amount + Tax*. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Not-to-exceed Limit | This field is editable and is only available on project-based quote lines that have a **Time and Material** billing method. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Customer Budget | This field is editable and is copied from the corresponding field on the opportunity line if the quote was created from an opportunity. | This value is copied to the project contract line that is created from this quote line when the quote is won. |


## Validation rules for fields on the General tab of project-based quote lines

**Rule 1**: If the **Included Tasks** field is blank, or if you set it to **All project tasks**, the quote line includes a project.

**Rule 2**: If the **Included Tasks** field is blank, or if you set it to **All project tasks**, a project and a certain transaction class can only be included on one project-based quote line of a quote.

**Rule 3**: If you set the **Included Tasks** field to **Selected project tasks only**, a project and a certain transaction class can be included on multiple project-based quote lines of a quote.

**Rule 4**: If an opportunity has multiple quotes, quote lines from different quotes can all reference the same project and include the same transaction class.

**Rule 5**: If the quotes don't belong to the same opportunity, they can't include the same project and transaction class.

| **Opportunity** | **Quote** | **Quote line** | **Project** | **Included tasks** | **Include Time** | **Include Expense** | **Include Material** | **Include Fee** | **Valid/ Not valid** | **Reason** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| O1 | Q1 | QL1 | P1 | Blank | Yes | Yes | Yes | Yes | Not valid | Violation of Rule #2. Time, Expense, and Fees on P1 project are included on quote lines QL1 and QL2 |
| O1 | Q1 | QL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | Blank | Yes | No | Yes | Yes | Not valid | Violation of Rule #2. Time, Material, and Fees on P1 project are included on quote lines QL1 and QL2 |
| O1 | Q1 | QL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | Blank | Yes | No | Yes | Yes | Valid | Time, Material, and Fees on P1 project are included on QL1. Expense on P1 project is included on QL2. No overlap in what is being included on each quote line and therefore valid. |
| O1 | Q1 | QL2 | P1 | Blank | No | Yes | No | No | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | Not valid | Violation of Rule #2. Q1 includes Time, Material, Expenses and Fees on a subset of tasks on project P1. QL2 includes Time, Expenses, and Fees for the whole project P1 and therefore overlaps with what is included on Q1. |
| O1 | Q1 | QL2 | P1 | Blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | Valid | Per Rule #3, Q1 includes Time, Material, Expenses, and Fees on a subset of tasks on project P1. QL2 includes Time, Material, Expenses, and Fees for a subset of tasks on project P1. The only additional validation is around the subset of tasks on QL1 which is different from the subset of tasks on QL2 to ensure that there is no overlap. The system checks this condition when you associate tasks. |
| O1 | Q1 | QL2 | P1 | Selected tasks only | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | All project tasks or blank | Yes | Yes | Yes | Yes | Valid | Per Rule #5, Q1 and Q2 are two quotes on the same opportunity, so they can both estimate for the same components of a project. |
| O1 | Q2 | QL1 | P1 | All project tasks or blank | Yes | Yes | Yes | Yes | | |
| | | | | | | | | | | |
| O1 | Q1 | QL1 | P1 | All project tasks or blank | Yes | Yes | Yes | Yes | Not Valid | Per Rule #4, Q1 and Q2 are two quotes on different opportunities, so they can't estimate for the same components of same project. |
| O2 | Q1 | QL1 | P1 | All project tasks or blank | Yes | Yes | Yes | Yes | | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
