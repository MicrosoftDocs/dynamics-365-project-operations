---
title: Project contract lines overview
description:  This article provides information about working with project contract lines in Project Operations.
author: rumant
ms.date: 12/03/2022
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant

---

# Project contract lines overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project-based contract lines in Dynamics 365 Project Operations are designed to hold the estimate and billing agreements for specific components of project work on an engagement. The structure of a project–based contract line is extended for project estimates and billing scenarios with the following concepts:

- Billing method
- Project and task mapping
- Included transaction classes
- Not-to-exceed limit
- Chargeability setup
- Estimates using contract line details
- Contract line customers

The following table includes the fields on the **General** tab of project–based contract lines that help set up the basis for a detailed, ground–up estimate and billing arrangements for project–based work.

| Field | Description | Downstream impact |
| --- | --- | --- |
| **Name** | Name of the contract line. This identifies the discrete component of the contract that is being estimated. For a project contract created from a quote, this value is copied from a corresponding value of the project-based quote line. | The name copied over to the project invoice line that is created from this contract line when the invoice is created. |
| **Billing Method** | On a project contract created from a quote, this value is copied from the corresponding field on the quote line. This is an option set that represents the two main contracting models supported by Project Operations:</br>- **Fixed Price**</br>- **Time and Material** | Based on the billing method of the referenced contract line, the actual transaction will be processed. If the contract line referenced by the actual has a time and material billing method, cost and unbilled sales actual records are created. If the contract line referenced by the actual has a fixed price billing method, only a cost actual is created. |
| **Invoice Schedule Type** | On a project contract created from a quote, this value is copied from the corresponding field on the quote line. This is an option set that represents the two Invoice Schedule Type for Fixed Price contracting model supported by Project Operations:</br>- **Completed Milestones**</br>- **Progress-based** | Invoice Schedule Type is only relevant for Fixed Price Billing method and  Based on the Invoice Schedule Type, Milestones are allowed to billed based on the progress % (Progress - based) or only when fully completed (Completed Milestones). Completed Milestones is the default value  |
| **Project** | Use this field to identify the project that will be used to deliver the work on this engagement. | This value will be used in conjunction with **Included Tasks** and **Included Transaction Classes** to resolve the contract line reference on an actual or estimate line record. |
| **Included Tasks** | Indicates if this contract line includes all project tasks for the selected project or only a subset of the tasks. This is an option set that has the following possible values:</br>- **All Project Tasks**</br>- **Selected Project Tasks Only**. A blank value in this field is equal to selecting **All Project Tasks**. | If **Selected Tasks Only** is selected, you can select specific tasks and associate them to this contract line on the **Task Billing Setup** tab on the **Project** page. The value will be used in conjunction with **Project** and **Included Transaction** classes to resolve the contract line reference on an actual or an estimate line record. |
| **Include Time** | A **Yes**/**No** value indicates if time transactions or labor costs on the selected project will be included on this contract line. A **No** value indicates that the time transactions or labor cost will not be included on this contract line. A **Yes** value indicates that they will. | This value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Expense** | A **Yes**/**No** value indicates if expense costs on the selected project will be included on this contract line. A **No** value indicates that the expense cost will not be included on this contract line. A **Yes** value indicates that it will. | This value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Materials** | A **Yes**/**No** value indicates if material costs on the selected project will be included on this contract line. A **No** value indicates that the material costs will not be included on this contract line. A **Yes** value indicates that it will. | This value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Include Fee** | A **Yes**/**No** value indicates if fees on the selected project will be included on this contract line. A **No** value indicates that the fees will not be included on this contract line. A **Yes** value indicates that they will. | This value is used in conjunction with the project to resolve the contract line reference on an actual or an estimate line record. |
| **Contracted Amount** | On a fixed price contract line, this amount is the agreed-on value that will be invoiced to the customer for all the work components associated to this contract line. On a time and material contract line, this amount is an estimated value of what will be invoiced to the customer for all the work components associated to this contract line. On a project contract that is created from a quote, this value is copied from the corresponding field on the quote line. When a project–based contract line has line details, this field is locked for editing and is summarized from the amount on the contract line details. | When the contract line has line details, this value can be modified by changing the amounts on the line details. On a fixed price contract line, this value is used to generate the amount before tax on periodic billing milestones. |
| **Estimated Tax** | The user can edit this field to input the estimated tax amount on the contract line. When a project–based contract line has line details, this field is locked for editing and is summarized from the tax amount on the contract line details. | When the contract line has line details, this value can be modified by changing the tax amounts on the line details. On a fixed price contract line, this value is used to generate the tax on periodic billing milestones. |
| **Contracted Amount after Tax** | The contract line amount after tax. This field is read only and is calculated as **Contracted Amount + Tax**. | On a fixed price contract line, this value is used to generate periodic billing milestones. |
| **Not-to-Exceed Limit** | The user can edit this field and it is only available on project-based contract lines that have the billing method set as time and material. | The user can edit this field. When an actual for time and material references this contract line for time and material, the amount on the actual is evaluated against the not-to-exceed limit on the contract line. This evaluation is completed after  the already spent and committed amounts are accounted for. |
| **Customer Budget** | This field is editable and is copied from the corresponding field on the quote line if the contract was created from a quote. | This field is only used for information and does not have any downstream significance. |

## Validation rules for the options on the General tab of project-based contract lines

Rule 1: If the **Included Tasks** field is blank or set to **All Project Tasks**, all tasks of the project are included on the contract line.

Rule 2: When the **Included Tasks** field is blank or explicitly set to **All Project Tasks**, a project and a certain transaction class can only be included on one project-based contract line of a contract.

Rule 3: When the **Included Tasks** field is set to **Selected Project Tasks Only**, a project and a certain transaction class can be included on multiple project-based contract lines of a contract.

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="43" valign="top">
                <p>
                    <strong>Contract</strong>
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    <strong>Contract line</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Project</strong>
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    <strong>Included tasks</strong>
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    <strong>Include Time</strong>
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    <strong>Include Expense</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Include Materials</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Include</strong>
                </p>
                <p>
                    <strong>Fee</strong>
                </p>
            </td>
            <td width="53" valign="top">
                <p>
                    <strong>Valid/ Not valid</strong>
                </p>
            </td>
            <td width="250" valign="top">
                <p>
                    <strong>Reason</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="53" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="250" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2. Time, Expense, Materials, and
                    Fees on P1 project are included on both Contract lines CL1
                    and CL2.
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
            </td>
            <td width="65" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="67" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="53" valign="top">
            </td>
            <td width="250" valign="top">
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="53" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="250" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2. Time, Materials, and Fees on P1
                    project are included on both Contract lines CL1 and CL2.
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
            </td>
            <td width="65" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="67" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="53" valign="top">
            </td>
            <td width="250" valign="top">
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="53" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="250" rowspan="2" valign="top">
                <p>
                    Time, Materials, and Fees on P1 project are included on
                    CL1.
                </p>
                <ul>
                    <li>
                        Expense on P1 project is included on CL2.
                    </li>
                </ul>
                <p>
                    No overlap in what is being included on each Contract
                    line and therefore valid.
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    No
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    No
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
            </td>
            <td width="65" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="67" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="53" valign="top">
            </td>
            <td width="250" valign="top">
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="53" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="250" rowspan="2" valign="top">
                <p>
                    Violation of Rule #2
                </p>
                <p>
                    C1 includes Time, Materials, Expenses and Fees on a subset
                    of tasks on project P1.
                </p>
                <p>
                    CL2 includes Time, Materials, Expenses and Fees for the
                    whole project P1 and therefore overlaps with what is
                    included on C1.
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Blank
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
            </td>
            <td width="65" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="67" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="53" valign="top">
            </td>
            <td width="250" valign="top">
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="53" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="250" rowspan="2" valign="top">
                <p>
                    Per Rule #3
                </p>
                <p>
                    C1 includes Time, Expenses, Materials, and Fees on a subset
                    of tasks on project P1.
                </p>
                <p>
                    CL2 includes Time, Expenses, Materials, and Fees for a
                    subset of tasks on project P1.
                </p>
                <p>
                    The only additional validation is around the subset of
                    tasks on CL1 is different from the subset of tasks on CL2
                    to ensure that there are no overlaps there. This is done by
                    the system when tasks are associated.
                </p>
            </td>
        </tr>
        <tr>
            <td width="43" valign="top">
                <p>
                    C1
                </p>
            </td>
            <td width="65" valign="top">
                <p>
                    CL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
                </p>
            </td>
            <td width="67" valign="top">
                <p>
                    Selected tasks only
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    Yes
                </p>
            </td>
        </tr>
    </tbody>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
