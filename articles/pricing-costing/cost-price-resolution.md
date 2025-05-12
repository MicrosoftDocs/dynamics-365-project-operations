---
title: Determine cost rates for project-based estimates and actuals
description: This article provides information about how cost rates for project-based estimates and actuals are determined.
author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Determine cost rates for project-based estimates and actuals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To determine cost prices on estimates and actuals in Microsoft Dynamics 365 Project Operations, the system first uses the date and currency in the incoming estimate or actual context to determine the sales price list. In the actual context specifically, the system uses the **Transaction date** field to determine which price list is applicable. The **Transaction date** value of the incoming estimate or actual is compared with the **Effective Start (Timezone independent)** and **Effective End (Timezone independent)** values on the price list. After the cost price list is determined, the system determines the cost rate.

## Determining cost rates in estimate and actual contexts for Time

Estimate context for **Time** refers to:

- Quote line details for **Time**.
- Contract line details for **Time**.
- Resource assignments on a project.

Actual context for **Time** refers to:

- Entry and Correction journal lines for **Time**.
- Journal lines that are created when a time entry is submitted.

After a cost price list is determined, the system completes the following steps to enter the default cost rate.

1. The system matches the combination of the **Role**, **Resourcing Company**, and **Resourcing Unit** fields in the estimate or actual context for **Time** against the role price lines on the price list. This matching assumes that you're using the standard pricing dimensions for labor cost. If you've configured the system to match fields other than or in addition to **Role**, **Resourcing Company** and **Resourcing Unit**, a different combination is used to retrieve a matching role price line.
1. If the system finds a role price line that has a cost rate for the **Role**, **Resourcing Company**, and **Resourcing Unit** combination, that cost rate is used as the default cost rate.
1. If the system can't match the **Role**, **Resourcing Company**, and **Resourcing Unit** values, it drops the dimension that has the lowest priority, searches for role price lines that have matches for the other two dimension values, and continues to progressively drop dimensions until a matching role price row is found. The cost rate from that record will be used as the default cost rate. If the system doesn't find a matching role price row, the price will be set to **0** (zero) by default.

> [!NOTE]
> If you configure a different prioritization of the **Role** and **Resourcing Unit** fields, or if you have other dimensions that have higher priority, the preceding behavior will change accordingly. The system retrieves role price records that have values that match each pricing dimension value in order of priority. Rows that have null values for those dimensions come last.

## Determining cost rates on actual and estimate lines for Expense

Estimate context for **Expense** refers to:

- Quote line details for **Expense**.
- Contract line details for **Expense**.
- Expense estimates on a project.

Actual context for **Expense** refers to:

- Entry and Correction journal lines for **Expense**.
- Journal lines that are created when an expense entry is submitted.

After a cost price list is determined, the system completes the following steps to enter the default cost rate.

1. The system matches the combination of the **Category** and **Unit** fields in the estimate or actual context for **Expense** against the category price lines on the price list.
1. If the system finds a category price line that has a cost rate for the **Category** and **Unit** combination, that cost rate is used as the default cost rate.
1. If the system can't match the **Category** and **Unit** values, the price is set to **0** (zero) by default.
1. In the estimation context, if the system can find a matching category price line, but the pricing method is something other than **Price Per Unit**, the cost rate is set to **0** (zero) by default.

## Determining cost rates on actual and estimate lines for Material

Estimate context for **Material** refers to:

- Quote line details for **Material**.
- Contract line details for **Material**.
- Material estimates on a project.

Actual context for **Material** refers to:

- Entry and Correction journal lines for **Material**.
- Journal lines that are created when a Material usage log is submitted.

After a cost price list is determined, the system completes the following steps to enter the default cost rate.

1. The system uses the combination of the **Product** and **Unit** fields in the estimate or actual context for **Material** against the price list item lines on the price list.
1. If the system finds a price list item line that has a cost rate for the **Product** and **Unit** combination, that cost rate is used as the default cost rate.
1. If the system can't match the **Product** and **Unit** values, the unit cost is set to **0** (zero) by default.
1. In the estimate or actual context, if the system can find a matching price list item line, but the pricing method is something other than **Currency amount**, the unit cost is set to **0** by default. This behavior occurs because Project Operations supports only the **Currency amount** pricing method for materials that are used on a project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
