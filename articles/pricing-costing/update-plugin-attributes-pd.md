---
title: Updating plug-in attributes with new pricing dimensions
description: This article provides information about how to update plug-in attributes for pricing dimensions.
author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---


# Update plug-in attributes with new pricing dimensions

[!INCLUDE[banner](../includes/banner.md)]

This article provides information about how to update plug-in attributes for pricing dimensions.

> [!NOTE]
> This article is only applicable to the quote and contract features in Dynamics 365 Project Operations.

## Prerequisites
Before you complete the steps in this article, you must have completed the procedures in the following articles:

  - [Create custom fields and entities](create-custom-fields-entities-pricing-dimensions.md) 
  - [Add custom fields to price setup and transactional entities](add-custom-fields-price-setup-transactional-entities.md)
  - [Set up custom fields as pricing dimensions](set-up-custom-fields-pricing-dimensions.md). 
  
If you haven't completed those procedures, complete them and then return to this article.

## Register a plug-in
When a quote line detail is created on the **Quote Line** page for a project quote line, the system creates two estimate lines. One line is for the cost side of the estimate and the other line is for sales the side. This is the same  for project contract lines.

When you make a change to the quantity or a field on the cost side, that change is also made on the sales side. This is possible because the PreOperation plug-ins on Quotelinedetail and contractline detail entities connect specific attributes on the cost side to the sales side of the transaction. If you need changes made to the pricing dimension values on the sales side to also be made on the cost side, the following plug-ins must be re-registered after making changes to a pricing dimension.

These are the plug-ins to update and re-register:

- PreOperationContractLineDetailUpdate - **Update msdyn_orderlinetransaction**
- PreOperationQuoteLineDetailUpdate - **Updates msdyn_quotelinetransaction**

Complete the following steps to update and re-register the plug-ins.

1. Open **PluginRegistrationTool** and connect to your Project Operations Dataverse environment.
2. Select **Search**, and type in the first few letters of the plug-in to be updated.
3. After the plug-in is found, select it, and then select **Select on Main Form**.
4. Select the **Update msdyn_orderlinetransaction** step, right-click, and then select **Update**.
5. In the **Update** dialog page, select the ellipsis (**...**) in the filtering attributes.
6. The filtering attributes window opens and provides a list of all attributes in the entity and the pricing dimensions. Select the check boxes for the pricing dimension attributes.
7. Select **OK** to close the page, and then select **Update Step**.
8. Repeat steps 2-7 for the second plug-in, **PreOperationQuoteLineDetail**. For this plug-in, you need to update the **Update of msdyn_quotelinetransaction** step.
9. Close **PluginRegistrationTool**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
