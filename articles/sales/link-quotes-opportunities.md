---
title: Create project quotes from opportunities
description: This article provides information about creating a project quote from an opportunity.
author: poojafandan
ms.author: poojafandan
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create project quotes from opportunities

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Quotes can be created from project opportunities in the following ways:

- From the **Quotes** tab on the **Project Opportunity** page
- From the Opportunity sales process flow
- By updating the opportunity reference on an existing quote

## From the Quotes tab of the Project Opportunity page

To create a project quote from an opportunity, complete the following steps.

1. Open the **Project Opportunity** page and select the **Quotes** tab. 
2. On the **Quotes** subgrid, select the **+** to create a new project quote based on the opportunity. All of the opportunity lines and related Project price lists are copied to the new quote from the opportunity.

## From the Opportunity sales process flow

To create a quote from the Opportunity sales process flow, complete the following steps.

1. From the Opportunity sales process flow, open the Opportunity.
2. Select the **Qualify** stage. 
3. Select **Next** and then select **+ Create** to create a new quote. Most of the information on the **Summary** tab for this new quote will have defaulted from the opportunity. 
4. Enter in any required information that is missing, or update defaulted values as necessary on the **Summary** tab,
5. Select **Save**. The new quote is created and associated to the opportunity. You can now view the quote information on the **Quotes** tab of the **Opportunity** page. 

   The Opportunity sales process moves to the next stage, **Propose**.


## By updating the opportunity reference on an existing quote

An existing quote can be linked to an Opportunity. Complete the following steps to update the Opportunity information on an existing quote.

1. Open the **Quote** page and select the **Summary** tab.
2. In the **Opportunity** field, select the opportunity that you want to link to the quote. You can see the quote in the **Quotes** grid of the Opportunity. 
3. Using the Opportunity sales process, the opportunity can be moved to the next stage, **Propose**. 

   When you move an opportunity to this stage, you can select this quote from a list of quotes associated with this opportunity. Selecting this quote indicates that you're moving forward with it.

   All the other quotes associated with the Opportunity will still be available and active until one of them is won. You can move the sales process back to the previous stage **Qualify**, and pick another quote to move forward with.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
