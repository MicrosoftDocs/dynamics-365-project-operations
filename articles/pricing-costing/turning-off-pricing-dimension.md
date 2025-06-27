---
title: Turning off a pricing dimension
description: This article provides information about how to turn off pricing dimensions.
author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Service industries
ms.author: abriccetti
ms.search.validFrom: 2020-10-01
---

# Turning off a pricing dimension

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

You might need to review and update your pricing strategy every few years. Any updates you make might require that you turn off an existing pricing dimension and create a new one. For example, you might have previously priced by **Role**, but now you decided to price by **Work Experience**. This might require you to turn off **Role** as a pricing dimension and create **Work Experience** as a new pricing dimension. 

You can turn off a pricing dimension, regardless if it's out-of-the-box or custom, can be done by setting the **Applicable to Cost** and **Applicable to Sales** fields of the Pricing Dimension to **No**.

However, when you do this, you might receive the error message, **Pricing dimension cannot be updated or deleted if there are associated price records.**

![Business Process Error likely when turning off a pricing dimension.](media/Business-Process-Error.png)

This error message indicates that there are price records that were previously set up for the dimension that is being turned off. All **Role Price** and **Role Price Markup** records that refer to a dimension must be deleted before the dimension’s applicability can be to set to **No**. This rule applies to both out-of-the-box pricing dimensions and any custom pricing dimensions that you created. The reason for this validation is because each **Role Price** record must have a unique combination of dimensions. For example, on a price list called **US Cost Rates 2018**, you have the following **Role price** rows. 

| Standard Title         | Org Unit    |Unit   |Price  |Currency  |
| -----------------------|-------------|-------|-------|----------|
| Systems Engineer|Contoso US|Hour| 100|USD|
| Senior Systems Engineer|Contoso US|Hour| 150| USD|


When you turn off **Standard Title** as the pricing dimension, and the pricing engine searches for a price, it only uses the **Org Unit** value from the input context. If the **Org Unit** of the input context is “Contoso US”, the result are  nondeterministic because both the rows match. To avoid this scenario, when you create **Role Price** records, the system validates that the combination of dimensions is unique. If the dimension is turned off after the **Role Price** records are created, this constraint can be violated. Therefore, it's required that before you turn off a dimension, you delete all **Role Price** and **Role Price Markup** rows that have that dimension value populated.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
