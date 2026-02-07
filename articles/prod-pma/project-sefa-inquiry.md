---
title: Schedule of Expenditures of Federal Awards inquiry
description: Learn how to run the Schedule of Expenditures of Federal Awards inquiry to track federal grant revenues and expenditures for audits and compliance.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: PSNProjSEFAinquiry 
ms.reviewer: johnmichalak
ms.search.validFrom: 2020-4-01
ms.dyn365.ops.version: 10.0.11
---

# Schedule of Expenditures of Federal Awards inquiry

[!include [banner](../includes/banner.md)]

According to Office of Management and Budget Circular A-133, agencies that receive federal funds must follow audit requirements, which are also known as single audits. Use the audit process to report on the revenues and expenditures of federal grants on a recurring basis. The Schedule of Expenditures of Federal Awards (SEFA) is part of the single audit report.

The Schedule of Expenditures of Federal Awards inquiry includes the Catalog of Federal Domestic Assistance (CFDA) title and number, the grant number, the year of the grant, the name of the federal agency that provides the funds, and the name of the pass-through entity. The inquiry is for a specific period. Typically, that period is the same as the financial statement period, which is a fiscal year.

The inquiry includes grants that have projection dates in the selected date range. The **Grantor agency** column of the inquiry shows the grant customer or, for a pass-through grant, the grantor agency. For a pass-through grant, the **Pass-through agency** column shows the grant customer. If the grant isn't a pass-through grant, the **Pass-through agency** column is blank.

## Set up the CFDA clusters

Set up the CFDA clusters that you can associate with CFDA numbers in the Schedule of Expenditures of Federal Awards inquiry.

1. Go to **Project management and accounting \> Setup \> Grants \> Catalog of Federal Domestic Assistance clusters**.
1. Select **New** to create a CFDA cluster.
1. Enter the cluster name.
1. Select **Save** to save your changes.

## Set up CFDA numbers

Set up CFDA numbers that you can add to grants and include in the Schedule of Expenditures of Federal Awards inquiry.

1. Go to **Project management and accounting \> Setup \> Grants \> Catalog of Federal Domestic Assistance numbers**.
1. Select **New** to create a CFDA number.
1. In the **Number** column, enter the CFDA number.
1. Press the **Tab** key.
1. In the **Description** column, enter the CFDA title.
1. Press the **Tab** key.
1. (Optional) In the **Program cluster** field, add the appropriate CFDA cluster.
1. Select **Save** to save your changes.

## Set up grants to report for the Schedule of Expenditures of Federal Awards inquiry

1. Go to **Project management and accounting \> Grants \> Grants**, and select an existing grant.
1. On the **Setup** FastTab, in the **Catalog of Federal Domestic Assistance** field, assign the CFDA number. The CFDA number on the grant determines the CFDA cluster for reporting.
1. On **Contact information** FastTab, enter the grantor information by following these steps:

    1. In the **Grant customer** field, enter the customer who is responsible for the grant. For an existing grant, this information might already be entered.
    1. Indicate whether the grant customer is the funder. If the grant customer is the funder, clear the **Pass-through** check box. If another customer is the funder, and the grant customer is responsible for spending and tracking the money, select the **Pass-through** check box.

1. If you selected the **Pass-through** check box in the previous step, in the **Grantor agency** field, enter the customer who provided the grant. The grantor agency and the grant customer can't be the same customer.

Here's an example of a pass-through grant:

The federal government funded an infrastructure project for a state. The federal government gave the money to the state to spend. In this case, the federal government is the grantor agency, and the state is the grant customer.

> [!NOTE]
> When you first turn on the feature, initial CFDA numbers are entered by using the existing numbers on grants.

## Exclude grants from SEFA reporting based on the grant type

1. Go to **Project management and accounting \> Setup \> Grants \> Grant types**.
1. On the **Default information** FastTab, select the **Exclude from Schedule of Expenditures of Federal Awards** check box.
1. Select **Save** to save your changes.

## Run the Schedule of Expenditures of Federal Awards inquiry

1. Go to **Project management and accounting > Inquiries and reports > Grant inquiry > Schedule of Expenditures of Federal Awards**.
1. In the **Parameters** section, follow these steps:

    1. In the **Date interval** field, select the code for the date interval. Alternatively, in the **From date** and **To date** fields, define the date interval.
    1. Optional: To include only billed transactions as revenue in the inquiry, set the **Include only billed revenues** option to **Yes**.

## Columns

The Schedule of Expenditures of Federal Awards inquiry includes the following columns:

- Catalog of Federal Domestic Assistance cluster name
- Grantor agency
- Pass-through agency
- Grant name
- Grant ID
- Grant application ID
- Catalog of Federal Domestic Assistance
- Receipts
- Expenditures

[!INCLUDE[footer-include](../includes/footer-banner.md)]
