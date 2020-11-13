---
title: Update plug-in attributes to include new pricing dimensions
description: This topic provides information about how to update plug-in attributes for pricing dimensions.
author: rumant
manager: Annbe
ms.date: 11/13/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: rumant
---


# Update plug-in attributes to include new pricing dimensions

> [!NOTE]
> This topic is only applicable to the quote and contract features in Dynamics 365 Project Operations.

## Prerequisites
Before you complete the steps in this topic, you must have completed the procedures in the following topics:

  - [Create custom fields and entities](create-custom-fields-entities-pricing-dimensions.md) 
  - [Add custom fields to price setup and transactional entities](add-custom-fields-price-setup-transactional-entities.md)
  - [Set up custom fields as pricing dimensions](set-up-custom-fields-pricing-dimensions.md). 
  
If you haven't completed those procedures, complete them and then return to this topic.

## Register a plug-in
When a quote line detail is created on the **Quote Line** page for a project quote line, the system creates two estimate lines in the background. One line is for the cost side of the estimate and the other line is for sales the side. This is the same  for project contract lines.

When you make a change to the quantity or a field on the cost side, that change is propagated to the sales side. This is possible because of the following plug-ins that must be re-registered after making changes to a pricing dimension.

These are the plug-ins you are registering:

- PreOperationContractLineDetailUpdate - Updates **msdyn_orderlinetransaction**.
- PreOperationQuoteLineDetailUpdate - Updates **msdyn_quotelinetransaction**.

Conmplete the following steps to register the plug-ins.

1. Open the **PluginRegistrationTool** and connect to your online instance.
2. Click **Search**, and search for the plug-in to be updated.
3. After the plug-in is found, select it and then click **Select on Main Form**.
4. Select the step of the plug-in to be updated, right-click, and then select **Update**.
5. In the update window, click the ellipsis (**...**) in the filtering attributes.
6. Select the pricing attribute check boxes.
7. Click **OK** to close the page and then select **Update Step**.
8. Repeat this process for the second plug-in, **PreOperationQuoteLineDetail - Update of msdyn_quotelinetransaction**.
9. Close the plug-in registration tool.

