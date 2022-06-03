---
title: Resolving cost prices for estimates and actuals
description: This article provides information about how cost prices for estimates and actuals are resolved.
author: rumant
ms.date: 04/09/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Resolving cost prices for estimates and actuals

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To resolve cost prices and the cost price list for estimates and actuals, the system uses the information in the **Date**, **Currency**, and **Contracting Unit** fields of the related project. After the cost price list is resolved, the application resolves the cost rate.

## Resolving cost rates on actual and estimate lines for Time

Estimate lines for Time refer to the quote and contract line details for time and resource assignments on a project.

After a cost price list is resolved, the system uses the **Role**, **Resourcing Company**, and **Resourcing Unit** fields on the estimate line for Time to match against the role price lines in the price list. This match assumes that you are using out-of-the-box pricing dimensions for labor cost. If you configured the system to match fields instead of, or in addition to **Role**, **Resourcing Company**, and **Resourcing Unit**, then a different combination will be used to retrieve a matching role price line. If the application finds a role price line that has a cost rate for the **Role**, **Resourcing Company**, and **Resourcing Unit** combination, that is the default cost rate. If the application can't exactly match the combination of **Role**, **Resourcing Company**, and **Resourcing Unit** values, it will retrieve role price lines with a matching role value, but have null values for **Resourcing Unit** and **Resourcing Company**. After a matching role price record with matching role price value is found, the cost rate defaults from that record. 

> [!NOTE]
> If you configure a different prioritization of **Role**, **Resourcing Company**, and **Resourcing Unit**, or if you have other dimensions that have higher priority, this behavior will change accordingly. The system retrieves role price records with values that match each of the pricing dimension values in order of priority with rows that have null values for those dimensions coming last in the priority order.

## Resolving cost rates on actual and estimate lines for Expense

Estimate lines for Expense refer to the quote and contract line details for expenses and the expense estimate lines on a project.

After a cost price list is resolved, the system uses a combination of the **Category** and **Unit** fields on the estimate line for an expense to match against the **Category Price** lines on the resolved price list. If the system finds a category price line that has a cost rate for the **Category** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Category** and **Unit** values, or if it is able to find a matching category price line but the pricing method is not **Price Per Unit**, the cost rate is defaulted to zero(0).

## Resolving cost rates on actual and estimate lines for material

Estimate lines for material refer to the quote and contract line details for materials and the material estimate lines on a project.

After a cost price list is resolved, the system uses a combination of the **Product** and **Unit** fields on the estimate line for a material estimate to match against the **Price List Items** lines on the resolved price list. If the system finds a product price line that has a cost rate for the **Product** and **Unit** field combination, the cost rate is defaulted. If the system can't match the **Product** and **Unit** values, the unit cost defaults to zero. This default will also happen if there is a matching price list item line, but the pricing method is based on a standard cost or current cost that isn't defined in the product.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
