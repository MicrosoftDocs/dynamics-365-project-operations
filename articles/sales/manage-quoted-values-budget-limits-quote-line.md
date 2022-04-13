---
title: Project quote lines overview
description: This topic provides information about using project quote lines for project work.
author: rumant
ms.date: 10/01/2020
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: rumant

---

# Project quote lines overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project-based quote lines are designed to help estimate the project work on an engagement. The structure of a project-based quote line is extended for project estimates with the following concepts:

- Billing Method
- Project Mapping
- Included Transaction classes
- Not-to-Exceed Limit
- Chargeability setup
- Estimation using Quote Line Details
- Quote line Customers

The following table provides information about the fields on the **General** tab of project-based quote line. These fields help set up the basis for a detailed, ground-up estimation for project work.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Name | The name of quote line which should help you identify the discrete component of the quote that is being estimated. | Copied to the project contract line that is created from this quote line when the quote is won. |
| Billing Method | On a quote created from an opportunity, this value is copied from the corresponding field on the opportunity line. This field includes the two main contracting models supported by Dynamics 365 Project Operations:</br>- Fixed price</br>- Time and material.| This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Project | Use this optional field to identify the project that will be used to deliver the work on this engagement. When a project is mapped to a quote line, it helps with setting up chargeable tasks and also with bringing in a project-based estimate to the quote line as quote line details. When a project is not mapped to a project-based quote line, the estimate should be created manually by creating each quote line detail. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Time | A **Yes**/**No** flag indicates if time transactions or labor costs on the selected project will be included in the estimate on this quote line. A **No** value indicates that the time transactions or labor cost will not be included in the estimate on this quote line. A **Yes** value indicates that the time transactions or labor cost will be included in the estimate on this quote line. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Include Expense | A **Yes**/**No** flag indicates if expense costs on the selected project will be included in the estimate on this quote line. A **No** value indicates that the expense cost will not be included in the estimate on this quote line. A **Yes** value indicates that the expense cost will be included in the estimate on this quote line. | This field value is copied over to the project contract line that is created from this quote line when the quote is won. |
| Include Fee | A **Yes**/**No** flag indicates if fees on the selected project will be included in the estimate on this quote line. A **No** value indicates that the Fees will not be included in the estimate on this quote line. A **Yes** value indicates that the Fees will be included in the estimate on this quote line. | This field value is copied to the Project contract line that is created from this quote line when the quote is won. |
| Quoted Amount | This is amount that will be quoted to the customer for all the work forecasted on this project-based quote line. On a quote created from an opportunity, this value is copied from the **Customer Budget** field on the opportunity line. When the project-based quote line has line details, this field is locked for editing and is summarized from the amount on the quote line details. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Estimated Tax | This is an editable field for the user to add the estimated tax amount on the quote line. When a project-based quote line has line details, this field is locked for editing and is summarized from the tax amount on the quote line details. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Quoted Amount after Tax | This field is the quote line amount after tax and is read-only. The amount in this field is calculated as *Quoted Amount + Tax*. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Not-to-exceed Limit | This field is editable and is only available on project-based quote lines that have a **Time and Material** billing method. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |
| Customer Budget | This field is editable and is copied from the corresponding field on the opportunity line if the quote was created from an opportunity. | This field value is copied to the project contract line that is created from this quote line when the quote is won. |

## Validation rules for fields on the General tab of project-based quote lines

**Rule 1**: A certain transaction class on the selected project can only be included on one project-based quote line of a quote.

**Rule 2**: If an opportunity has multiple quotes, there can be quote lines from different quotes that all reference the same project and include the same transaction class.

**Rule 3**: If the quotes do not belong to the same opportunity, they can't include the same project and transaction class.

<table border="1" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="61" valign="top">
                <p>
                    <strong>Opportunity</strong>
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    <strong>Quote</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Quote line</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Project</strong>
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    <strong>Include time</strong>
                </p>
            </td>
            <td width="48" valign="top">
                <p>
                    <strong>Include expense</strong>
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    <strong>Include</strong>
                </p>
                <p>
                    <strong>fee</strong>
                </p>
            </td>
            <td width="54" valign="top">
                <p>
                    <strong>Valid/ Not valid</strong>
                </p>
            </td>
            <td width="308" valign="top">
                <p>
                    <strong>Reason</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                <p>
                    Violation of Rule #1. Time, Expense, and Fees on P1
                    project are included on both quote lines, QL1 and QL2.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
        </tr>
        <tr>
            <td width="61" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="54" valign="top">
            </td>
            <td width="308" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                <p>
                    Violation of Rule #1. Time and Fees on P1 project are
                    included on both quote lines, QL1 and QL2.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
        </tr>
        <tr>
            <td width="61" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="54" valign="top">
            </td>
            <td width="308" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" rowspan="2" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                 <p>
                 Time and fees on P1 project are included on QL1.
                 Expense on P1 project is included on QL2.
                 There is no overlap in what is being included on each quote line
                 so it is valid.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
        </tr>
        <tr>
            <td width="61" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="54" valign="top">
            </td>
            <td width="308" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" rowspan="2" valign="top">
                <p>
                    Not valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                <p>
                    Violation of Rule #1 above
                </p>
                <p>
                    Q1 includes Time, Expenses, and Fees for the whole project
                    P1.
                </p>
                <p>
                    QL2 includes Time, Expenses, and Fees for the whole project
                    P1 and overlaps with what is included on Q1.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
        </tr>
        <tr>
            <td width="61" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="54" valign="top">
            </td>
            <td width="308" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                <p>
                    Based on Rule #2, Q1 and Q2 are two quotes on the same opportunity, so
                    they can both estimate for the same components of a
                    project.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1 on Q2
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
            </td>
            <td width="41" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="48" valign="top">
            </td>
            <td width="42" valign="top">
            </td>
            <td width="54" valign="top">
            </td>
            <td width="308" valign="top">
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O1
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" valign="top">
                <p>
                    Valid
                </p>
            </td>
            <td width="308" rowspan="2" valign="top">
                <p>
                    Based on Rule #3, Q1 and Q2 are two quotes on different
                    opportunities, so they can't estimate for the same
                    components of the same project.
                </p>
            </td>
        </tr>
        <tr>
            <td width="61" valign="top">
                <p>
                    O2
                </p>
            </td>
            <td width="41" valign="top">
                <p>
                    Q1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    QL1
                </p>
            </td>
            <td width="42" valign="top">
                <p>
                    P1
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
            <td width="54" valign="top">
                <p>
                    Not Valid
                </p>
            </td>
        </tr>
    </tbody>
</table>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
