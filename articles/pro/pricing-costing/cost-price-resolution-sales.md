---
title: Resolve cost prices on project estimates and actuals
description: This article provides information about how cost prices on project estimates and actuals are resolved.
author: rumant
ms.date: 04/07/2021
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: rumant
---

# Resolve cost prices on project estimates and actuals 

_**Applies To:** Lite deployment - deal to proforma invoicing_

To resolve cost prices and the cost price list for estimates and actuals, the system uses the information in the **Date**, **Currency**, and **Contracting Unit** fields of the related project. After the cost price list is resolved, the application resolves the cost rate.

## Resolving cost rates on actual and estimate lines for Time

Estimate lines for Time refer to the quote and contract line details for time and resource assignments on a project.

After a cost price list is resolved, the **Role** and **Resourcing Unit** fields on the estimate line for Time are matched against the role price lines in the price list. This match assumes that you're using the standard pricing dimensions for labor cost. If you configured the system to match fields instead of, or in addition to **Role** and **Resourcing Unit**, then a different combination will be used to retrieve a matching role price line. If the application finds a role price line that has a cost rate for the **Role** and **Resourcing Unit** combination, that is the default cost rate. If the application can't match the **Role** and **Resourcing Unit** values, then it retrieves role price lines with a matching role, but null values of the **Resourcing Unit**. After it has a matching role price record, the cost rate defaults from that record. 

> [!NOTE]
> If you configure a different prioritization of **Role** and **Resourcing Unit**, or if you have other dimensions that have higher priority, this behavior will change accordingly. The system retrieves role price records with values that match each of the pricing dimension values in order of priority with rows that have null values for those dimensions coming last.

## Resolving cost rates on actual and estimate lines for Expense

Estimate lines for Expense refer to the quote and contract line details for expenses and the expense estimate lines on a project.

After a cost price list is resolved, the system uses a combination of the **Category** and **Unit** fields on the expense estimate line to match against the **Category Price** lines on the resolved price list. If the system finds a category price line that has a cost rate for the **Category** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Category** and **Unit** values, or if it's able to find a matching category price line but the pricing method isn't **Price Per Unit**, the cost rate defaults to zero(0).

## Resolving cost rates on actual and estimate lines for Material

Estimate lines for Material refer to the quote and contract line details for materials and the material estimate lines on a project.

After a cost price list is resolved, the system uses a combination of the **Product** and **Unit** fields on the estimate line for a material estimate to match against the **Price List Items** lines on the resolved price list. If the system finds a product price line that has a cost rate for the **Product** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Product** and **Unit** values, or if it's able to find a matching price list item line but the pricing method is based on Standard cost or Current cost and neither is defined on the product, the unit cost defaults to zero.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
