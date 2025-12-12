---
title: Project quote lines overview 
description: This article provides information about using project-based quote lines for project work.
author: poojafandan
ms.date: 06/10/2024
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan

---

# Project quote lines overview 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

Project-based quote lines are designed to help estimate the project work on an engagement. The structure of a project-based quote line is extended for project estimates with the following concepts:

- Billing Method
- Project and Task Mapping
- Included Transaction classes
- Not-to-Exceed Limit
- Chargeability setup
- Estimation using Quote Line Details
- Quote line Customers

The following table provides information about the fields on the **General** tab of project-based quote line. These fields help set up the basis for a detailed, ground-up estimation for project work.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Name | The name of quote line that helps you to identify the discrete component of the quote that is being estimated. | Copied to the project contract line that is created from this quote line when the quote is won. |
| Billing Method | On a quote created from an opportunity, this value is copied from the corresponding field on the opportunity line. This field includes the two main contracting models supported by Dynamics 365 Project Operations:</br>- Fixed price</br>- Time and material.| This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Project | Use this optional field to identify the project that will be used to deliver the work on this engagement. When a project is mapped to a quote line, it helps with setting up chargeable tasks and also with bringing in a project-based estimate to the quote line as quote line details. When a project is not mapped to a project-based quote line, the estimate should be created manually by creating each quote line detail. | This value is copied to the project contract line that is created from this quote line when the quote is won.|
| Included Tasks | Indicates if this quote line is used for all or some of the project tasks for the selected project. This field has the following possible values:</br>- All project tasks</br>- Selected project tasks only</br>A blank value in this field is equivalent to the **All project tasks** option. | When **Selected project tasks only** is selected on the project page, the **Task billing setup** tab allows you to select specific tasks to associate them to this quote line. This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Time | A **Yes**/**No** value indicates if time transactions or labor costs on the selected project will be included in the estimate on this quote line. A **No** value indicates that the time transactions or labor cost will not be included in the estimate on this quote line. A **Yes** value indicates that the time transactions or labor cost will be included in the estimate on this quote line. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Expense | A **Yes**/**No** value indicates if expense costs on the selected project will be included in the estimate on this quote line. A **No** value indicates that the expense cost will not be included in the estimate on this quote line. A **Yes** value indicates that the expense cost will be included in the estimate on this quote line. | This value is copied over to the project contract line that is created from this quote line when the quote is won. |
| Include Material | A **Yes**/**No** value indicates if material costs on the selected project will be included in the estimate on this quote line. A **No** value indicates that the material costs will not be included in the estimate on this quote line. A **Yes** value indicates that the material costs will be included in the estimate on this quote line. | This value is copied over to the project contract line that is created from this quote line when the quote is won. |
| Include Fee | A **Yes**/**No** value indicates if fees on the selected project will be included in the estimate on this quote line. A **No** value indicates that the fees will not be included in the estimate on this quote line. A **Yes** value indicates that the fees will be included in the estimate on this quote line. | This value is copied to the Project contract line that is created from this quote line when the quote is won. |
| Quoted Amount | This is the amount that will be quoted to the customer for all the work forecasted on this project-based quote line. On a quote created from an opportunity, this value is copied from the **Customer Budget** field on the opportunity line. When the project-based quote line has line details, this field is locked for editing and is summarized from the amount on the quote line details. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Estimated Tax | This is an editable field for the user to add the estimated tax amount on the quote line. When a project-based quote line has line details, this field is locked for editing and is summarized from the tax amount on the quote line details. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Quoted Amount after Tax | This field is the quote line amount after tax and is read-only. The amount in this field is calculated as *Quoted Amount + Tax*. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Not-to-exceed Limit | This field is editable and is only available on project-based quote lines that have a **Time and Material** billing method. | This value is copied to the project contract line that is created from this quote line when the quote is won. |
| Customer Budget | This field is editable and is copied from the corresponding field on the opportunity line if the quote was created from an opportunity. | This value is copied to the project contract line that is created from this quote line when the quote is won. |


## Validation rules for fields on the General tab of project-based quote lines

**Rule 1**: If the **Included Tasks** field is blank, or if it is set to **All project tasks**, a project is included in the quote line.

**Rule 2**: If the **Included Tasks** field is blank, or if it is set to **All project tasks**, a project and a certain transaction class can only be included on one project-based quote line of a quote.

**Rule 3**: If the **Included Tasks** field is set to **Selected project tasks only**, a project and a certain transaction class can be included on multiple project-based quote lines of a quote.

**Rule 4**: If an opportunity has multiple quotes, there can be quote lines from different quotes that all reference the same project and include the same transaction class.

**Rule 5**: If the quotes do not belong to the same opportunity, they can't include the same project and transaction class.

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="59" valign="top">
                <p>
                    <strong>Opportunity</strong>
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    <strong>Quote</strong>
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    <strong>Quote line</strong>
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    <strong>Project</strong>
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    <strong>Included tasks</strong>
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    <strong>Include Time</strong>
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    <strong>Include Expense</strong>
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    <strong>Include Material</strong>
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    <strong>Include</strong>
                </p>
                <p>
                    <strong>Fee</strong>
                </p>
            </td>
            <td width="49" valign="top">
                <p>
                    <strong>Valid/ Not valid</strong>
                </p>
            </td>
            <td width="200" valign="top">
                <p>
                    <strong>Reason</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2. Time, Expense, and Fees on P1
                    project are included on quote lines QL1 and QL2
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2. Time, Material, and Fees on P1
                    project are included on quote lines QL1 and QL2
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Time, Material, and Fees on P1 project are included on QL1 <br>
                    Expense on P1 project is included on QL2 <br>
                    No overlap in what is being included on each quote line and therefore valid.
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    No
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2
                </p>
                <p>
                    Q1 includes Time, Material, Expenses and Fees on a subset
                    of tasks on project P1
                </p>
                <p>
                    QL2 includes Time, Expenses, and Fees for the whole project
                    P1 and therefore overlaps with what is included on Q1.
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Per Rule #3,
                </p>
                <p>
                    Q1 includes Time, Material, Expenses, and Fees on a subset
                    of tasks on project P1.
                </p>
                <p>
                    QL2 includes Time, Material, Expenses, and Fees for a subset
                    of tasks on project P1.
                </p>
                <p>
                    The only additional validation is around the subset of
                    tasks on QL1 which is different from the subset of tasks on QL2
                    to ensure that there is no overlap. This is done by
                    the system when tasks are associated.
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    All project tasks or blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Per Rule #5, Q1 and Q2 are two quotes on the same opportunity, so
                    they can both estimate for the same components of a
                    project.
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q2
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    All project tasks or blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
            </td>
            <td width="39" valign="top">
            </td>
            <td width="40" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="77" valign="top">
            </td>
            <td width="45" valign="top">
            </td>
            <td width="46" valign="top">
            </td>
            <td width="43" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="49" valign="top">
            </td>
            <td width="200" valign="top">
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    All project tasks or blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="49" rowspan="2" valign="top">
                <p>
                    Not Valid
                </p>
            </td>
            <td width="200" rowspan="2" valign="top">
                <p>
                    Per Rule #4, Q1 and Q2 are two quotes on different
                    opportunities, so they can't estimate for the same
                    components of same project.
                </p>
            </td>
        </tr>
        <tr>
            <td width="59" valign="top">
                <p>
                    O2
                </p>
            </td>
            <td width="39" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="40" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="77" valign="top">
                <p>
                    All project tasks or blank
                </p>
            </td>
            <td width="45" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="46" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="43" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
    </tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
