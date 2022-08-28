---
title: Determine cost rates on project estimates and actuals
description: This article provides information about how cost rates on project estimates and actuals are determined.
author: rumant
ms.date: 04/07/2021
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: rumant
---

# Determine cost rates on project estimates and actuals 

_**Applies To:** Lite deployment - deal to proforma invoicing_

To determine cost price list and cost rates in the estimates and actuals contexts, the application uses the information in the **Date**, **Currency**, and **Contracting Unit** fields of the related project. 

## Determining cost rates on estimate and actual contexts for Time

Estimate context for Time refers to 
- Quote line details for time
- Contract line details for time 
- Resource assignments on a project.

Actual context for Time refers to 
- Entry and Correction journal lines for time
- Journal lines created when a time entry is submitted

After determining the cost price list, the **Role** and **Resourcing Unit** fields on the estimate context or actual context for Time are matched against the role price lines in the price list. This match assumes that you're using the standard pricing dimensions for labor cost. If you configured the application to match fields instead of, or in addition to **Role** and **Resourcing Unit**, then a different combination will be used to retrieve a matching role price line. If the application finds a role price line that has a cost rate for the **Role** and **Resourcing Unit** combination, that is the default cost rate. If the application can't match the **Role** and **Resourcing Unit** values, then it retrieves role price lines with a matching role, but null values of the **Resourcing Unit**. After it has a matching role price record, the cost rate defaults from that record. 

> [!NOTE]
> If you configure a different prioritization of **Role** and **Resourcing Unit**, or if you have other dimensions that have higher priority, this behavior will change accordingly. The application retrieves role price records with values that match each of the pricing dimension values in order of priority with rows that have null values for those dimensions coming last.

## Determining cost rates on actual and estimate lines for Expense

Estimate context for Expense refers to 
- Quote line details for expense
- Contract line details for expense 
- Expense estimates on a project.

Actual context for Expense refers to 
- Entry and Correction journal lines for Expense
- Journal lines created when an expense entry is submitted

After a cost price list is determined, the application uses a combination of the **Category** and **Unit** fields on the estimate and actual context of the expense to match against the **Category Price** lines on the cost price list. If the application finds a category price line that has a cost rate for the **Category** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Category** and **Unit** values then price defaults to O. In the estimation context, if the application is able to find a matching category price line but the pricing method isn't **Price Per Unit**, the cost rate defaults to zero(0).  

## Determining cost rates on actual and estimate lines for Material

Estimate context for Material refers to 
- Quote line details for Material
- Contract line details for Material 
- Material estimates on a project.

Actual context for Material refers to 
- Entry and Correction journal lines for Material
- Journal lines created when an Material usage log is submitted


After a cost price list is determined, the system uses a combination of the **Product** and **Unit** fields on the estimate and actual context for a material to match against the **Price List Items** lines on the price list. If the application finds a price list item that has a cost rate for the **Product** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Product** and **Unit** values, the unit cost defaults to zero.
IF application is able to find a matching price list item line but the pricing method is not Currency amount, then unit cost default to 0 on the estimate or actual context. This is because currently Project Operations does not support any pricing method other than Currency amount on materials used on project.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
