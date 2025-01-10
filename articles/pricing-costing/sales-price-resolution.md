---
title: Determine sales prices for project-based estimates and actuals
description: This article provides information about how sales prices for project-based estimates and actuals are determined.
author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

#  Determine sales prices for project-based estimates and actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To determine sales prices on estimates and actuals in Microsoft Dynamics 365 Project Operations, the system first uses the date and currency in the incoming estimate or actual context to determine the sales price list. In the actual context specifically, the system uses the **Transaction date** field to determine which price list is applicable. The **Transaction date** value of the incoming estimate or actual is compared with the **Effective Start (Timezone independent)** and **Effective End (Timezone independent)** values on the price list. After the sales price list is determined, the system determines the sales or bill rate.

## Determining sales rates on actual and estimate lines for Time

Estimate context for **Time** refers to:

- Quote line details for **Time**.
- Contract line details for **Time**.
- Resource assignments on a project.

Actual context for **Time** refers to:

- Entry and Correction journal lines for **Time**.
- Journal lines that are created when a time entry is submitted.
- Invoice line details for **Time**. 

After a price list for sales is determined, the system completes the following steps to enter the default bill rate.

1. The system matches the combination of the **Role**, **Resourcing Company**, and **Resourcing Unit** fields in the estimate or actual context for **Time** against the role price lines on the price list. This matching assumes that you're using the out-of-box pricing dimensions for bill rates. If you've configured pricing so that it's based on fields other than or in addition to **Role**, **Resourcing Company**, and **Resourcing Unit**, that combination of fields is used to retrieve a matching role price line.
1. If the system finds a role price line that has a bill rate for the **Role**, **Resourcing Company**, and **Resourcing Unit** combination, that bill rate is used as the default bill rate.

> [!NOTE]
> If you configure a different prioritization of the **Role**, **Resourcing Company**, and **Resourcing Unit** fields, or if you have other dimensions that have higher priority, the preceding behavior will change accordingly. The system retrieves role price records that have values that match each pricing dimension value in order of priority. Rows that have null values for those dimensions come last.

## Determining sales rates on actual and estimate lines for Expense

Estimate context for **Expense** refers to:

- Quote line details for **Expense**.
- Contract line details for **Expense**.
- Expense estimate lines on a project.

Actual context for **Expense** refers to:

- Entry and Correction journal lines for **Expense**.
- Journal lines that are created when an expense entry is submitted.
- Invoice line details for **Expense**. 

After a price list for sales is determined, the system completes the following steps to enter the default unit sales price.

1. The system matches the combination of the **Category** and **Unit** fields on the estimate line for **Expense** against the category price lines on the price list.
1. If the system finds a category price line that has a sales rate for the **Category** and **Unit** combination, that sales rate is used as the default sales rate.
1. If the system finds a matching category price line, the pricing method might be used to enter the default sales price. The following table shows the defaulting behavior for expense prices in Project Operations.

    | Context | Pricing method | Default price |
    | --- | --- | --- |
    | Estimate | Price per unit | Based on the category price line. |
    |        | At cost | 0.00 |
    |        | Markup over cost | 0.00 |
    | Actual | Price per unit | Based on the category price line. |
    |        | At cost | Based on the related cost actual. |
    |        | Markup over cost | A markup is applied, as defined by the category price line, to the unit cost rate of the related cost actual. |

1. If the system can't match the **Category** and **Unit** values, the sales rate is set to **0** (zero) by default.

## Determining sales rates on actual and estimate lines for Material

Estimate context for **Material** refers to:

- Quote line details for **Material**.
- Contract line details for **Material**.
- Material estimate lines on a project.

Actual context for **Material** refers to:

- Entry and Correction journal lines for **Material**.
- Journal lines that are created when a Material usage log is submitted.
- Invoice line details for **Material**. 

After a price list for sales is determined, the system completes the following steps to enter the default unit sales price.

1. The system matches the combination of the **Product** and **Unit** fields on the estimate line for **Material** against the price list item lines on the price list.
1. If the system finds a price list item line that has a sales rate for the **Product** and **Unit** combination, and if the pricing method is **Currency amount**, the sales price that is specified on the price list line is used. 
1. If the **Product** and **Unit** field values aren't a match, or if the pricing method is something other than **Currency amount**, the sales rate is set to **0** (zero) by default. This behavior occurs because Project Operations supports only the **Currency amount** pricing method for materials that are used on a project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
