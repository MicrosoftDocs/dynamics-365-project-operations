---
title: Product opportunity lines
description: This article provides information about product opportunity line items in Project Operations.
author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Product opportunity lines

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Product opportunity lines are line items on the Opportunity that do not reference a project. These distinct line items are on the eventual invoice that is provided to the customer. The invoice doesn't include any other additional services. The associated spend and consumption isn't tracked on tasks of any related projects.

Product-based lines can be catalog items or write-in products. Most of the functionality on an Opportunity's product-based lines follows the functionality provided by the Dynamics 365 Sales application. For more information about product-based opportunity lines, see [Add products to an opportunity](/dynamics365/sales-enterprise/add-products-opportunity).

**Customer budget** is a concept that is specific to project-based opportunity lines. The **Customer budget** field tracks the amount the customer is willing to pay for the item.

When the revenue method of the Opportunity summary is **System Calculated**, the customer budget values across the opportunity lines are summarized to calculate the estimated revenue. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
