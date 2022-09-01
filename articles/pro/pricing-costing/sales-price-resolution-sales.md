---
title: Determine sales prices for project estimates and actuals
description: This article provides information about determining sales prices on project estimates and actuals.
author: rumant
ms.date: 09/01/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Determine sales prices for project estimates and actuals

_**Applies To:** Lite deployment - deal to proforma invoicing_

When determining sales prices on estimates and actuals in Dynamics 365 Project Operations, the system first uses the date and currency of the incoming estimate or actual context to determine the sales price list. In the actual context specifically, the system will use the **Transaction date** field to determine which price list is applicable. After the sales price list is determined, the system determines the sales or bill rate.

## Determine sales rates on actual and estimate lines for Time

Estimate context for **Time** refers to:

- Quote line details for **Time**.
- Contract line details for **Time**.
- Resource assignments on a project.

Actual context for **Time** refers to:

- Entry and Correction journal lines for **Time**.
- Journal lines created when a time entry is submitted.
- Invoice line details for **Time**. 

After a price list for sales is determined, the system completes the following steps to default the bill rate.

1. The system uses the **Role** and **Resourcing Unit** fields on the estimate / actual context for time, to match against the role price lines in the price list. This matching assumes that out-of-box pricing dimensions for bill rates are being used. If you have configured pricing based on any other fields, instead of or in addition to **Role** and **Resourcing Unit**, then that is the combination that is used to retrieve a matching role price line.
1. If the system finds a role price line that has a bill rate for the **Role** and **Resourcing Unit** field combination, then that bill rate is defaulted.
1. If the system is unable to match the **Role** and **Resourcing Unit** field values, then it retrieves role price lines with a matching role but null values of **Resource Unit**. After the system finds a matching role price record, it will default the bill rate from that record. This matching assumes an out-of-the-box configuration for the relative priority of **Role** vs **Resourcing Unit** as a sales pricing dimension.

> [!NOTE]
> If you configured a different prioritization of **Role** and **Resourcing Unit**, or if you have other dimensions that have higher priority, this behavior will change accordingly. The system retrieves the role price records with matching values of each of the pricing dimension values in the order of priority with rows that have null values for those dimensions coming last.

## Determine sales rates on actual and estimate lines for Expense

Estimate context for **Expense** refers to:

- Quote line details for **Expense**.
- Contract line details for **Expense**.
- Expense estimate lines on a project.

Actual context for **Expense** refers to:

- Entry and Correction journal lines for **Expense**.
- Journal lines created when a Expense entry is submitted.
- Invoice line details for **Expense**. 

After a price list for sales is determined, the system completes the following steps to default the unit sales price.

1. The system uses the **Category** and **Unit** field combination on the estimate line for expense to match against the category price lines in the price list that was resolved.
1. If the system finds a category price line that has a sales rate for the **Category** and **Unit** field combination, then that sales rate is defaulted.
1. If the system finds a matching category price line, the pricing method may be used to default the sales price. The following table below shows the expense price defaulting behavior in Project Operations.

    | Context | Pricing method | Price defaulted |
    | --- | --- | --- |
    | Estimate | Price per unit | Based on the category price line. |
    | &nbsp; | At cost | 0.00 |
    | &nbsp; | Markup over cost | 0.00 |
    | Actual | Price per unit | Based on the category price line. |
    | &nbsp; | At cost | Based on the related cost actual. |
    | &nbsp; | Markup over cost | Apply a markup as defined by the category price line on the unit cost rate of the related cost actual. |

1. If the system is unable to match the **Category** and **Unit** field values, the sales rate defaults to zero (0).

## Determine sales rates on actual and estimate lines for Material

Estimate context for **Material** refers to:

- Quote line details for **Material**.
- Contract line details for **Material**.
- Material estimate lines on a project.

Actual context for Material refers to

- Entry and Correction journal lines for **Material**.
- Journal lines created when a Material usage log is submitted.
- Invoice line details for **Material**. 

After a price list for sales is determined, the system completes the following steps to default the unit sales price.

1. The system uses the **Product** and **Unit** field combination on the estimate line for material to match against the price list item lines in the price list that was resolved.
1. If the system finds a price list item line that has a sales rate for the **Product** and **Unit** field combination and the pricing method is **Currency amount**, the sales price that is specified on the price list line is used. 
1. If the **Product** and **Unit** field values aren't a match, or the pricing method is anything other than **Currency amount**, the sales rate defaults to zero (0). This is because Project Operations does not support any pricing method other than **Currency amount** on materials used for the project.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
