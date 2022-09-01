---
title: Activate and revise a project quote
description: This article provides information about activating and revision quotes in Project Operations.
author: rumant
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Activate and revise a project quote

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Activation and Revision of quotes helps to keep track of versioning of project quotes during the estimation and negotiation phases. When a draft quote is activated, it becomes read-only. With activation and revisions capability, you will be able to 
a. Win or lose quotes only after activation
b. You will be able to revise a quote to create a new version of the existing quote and make changes. 
To turn on the ability to activate and revise project-based quotes, follow these steps: 
1. Navigate to Settings-> Parameters
2. Open the parameters record and open the ribbon menu at the top for **Feature Control**
3. In the **Feature Control** ribbon menu, click on **Enable activation and revision of quotes**
4. In the confirmation dialog, select **Ok**. 
5. Give a few moments and refresh your browser. Activation and REvision capabilities will become avaialble. It is best to make sure that the capability is turned by checking the ribbon menu to ensure that the option to **Enable activation and revision fpr quotes** should no longer be listed in the menu options. 

> [!NOTE]
> Enabling the feature for activation and revision of quotes is a one-way operation. The feature once enabled cannot be disabled.

## Activating a quote

Once the feature Activation and revision of quotes is enabled, on a draft project quote, the buttons Close quote as Won and Close quote as lost will not be available. These buttons will be avaialble once a quote is activated. 
Activation represents a stage in the quoting process when you would like to lock the quote from any more changes. At this stage the quote is usually sent for internal review or to the customer. 
An activated quote will have the ribbon buttons for **Close quote as Won** and **Close quote as lost** avaialble. You can close an activated quote using these buttons based on the outcome of internal or customer reviews.
Negotiation and changes can be made on activated quotes using the **Revise quote** action

## Revising a quote
If you need to make any changes to an activated quote, click the ribbon action to **Revise quote**. This will close the quote with the reason **revised** and will create a new quote with the same id but with incremented revision number. 
All the details from the original quote are copied to the newly created revision. The newly created quote will be in draft status and can be edited as necessary. 





[!INCLUDE[footer-include](../includes/footer-banner.md)]
