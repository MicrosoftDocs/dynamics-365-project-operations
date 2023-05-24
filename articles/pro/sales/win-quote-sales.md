---
title: Close project quotes
description: This article provides information about closing a quote in Project Operations.
author: rumant
ms.date: 12/03/2022
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: rumant
---

# Close project quotes

_**Applies To:** Lite deployment - deal to proforma invoicing_

A project quote can be closed as Won or Lost. A draft quote can be closed because the Activate and Revise operations on quotes isn't supported in Microsoft Dynamics 365 Project Operations.

## Close a quote as Won

When you close a project quote as Won, the status is set to Closed and the status reason is Won. Closing the quote makes the project quote read-only and creates a draft project contract that contains the quote information. Because a closed quote can't be reopened, a confirmation dialog will confirm your changes.

If the quote is attached to an opportunity, any other project quotes on the opportunity are automatically closed as Lost.

### Financial impact of closing a quote as Won

If there are any actuals for time on a project while is still attached to a draft quote, only the cost of the time or expense is recorded. 
After a quote is closed as Won, the application will refactor the costs by reversing the older cost actuals and re-creating new cost actuals. The application will process these cost actuals based on the Billing method of the associated project contract line. If the cost actuals reference a time and material contract line, corresponding unbilled sales actuals are created for when the quote is closed and the project contract is created. If the cost actuals reference a fixed price contract line, the application will stop reprocessing the cost actuals that are based on the split billing rules for the project contract customers.

### Managing how price lists attached to the quote are handled during Quote win

When winning a quote in Project Operations, the application provides options to you on how to transfer Price Lists from Quote to the Project Contract. There are 3 options available. To access these options navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **During Contract creation from Quote**. You will see 3 options:

Option 1 - **Associate quote price lists to Project Contract**: 
Selecting this option will attach the same price list(s) on the quote to the Project contract. Of the 3 options, this option will give the best performance for Quote win since there is only one new record that is created from a pricing standpoint. However, selecting this option when a standard price list is used will expose the contract to any price changes that are made in this price list. So it the prices used when building the quote may deviate from the prices used during the execution of the project if prices in the price list got update after winning the quote. 

Option 2 - **Associate quote price lists to Project Contract with contract-specific price overrides for components estimated on the quote**: 
Selecting this option will create contract scoped price overrides for all the components estimated on Quote line details. Selecting this option will create date effective price overrides scoped to the contract for estimated components i.e. components referenced on quote line details. Due to these price overrides, any price changes in the price list for these components  will not impact how the actuals are priced during the execution of the project. This option will not create an entire copy of the quote price list and therefore will give much better performance than selecting Option 3 below. However, it will be slower than Option 1 since it will lead to the creation of Date effective price overrides for components reference on quote line details. Depedning on the number of quote line details, this could take longer to win the quote or be very quick to win the quote if the Quote had only a few Quote line details.

Option 3 - **Make copies of quote price lists and associate them to Project Contract**: 
Selecting this option will create a full copy of the quote price list with the name of the contract and date appended and attach this full copy to the Project contract. Of the 3 options, this option will have a severe impact on the performance of Quote win and the time it take to create the Project Contract. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that was used during quote stage for the duration of the Project. 

## Closing a quote as lost

When you close a project quote as Lost, the status is set to Closed and status reason is Lost. Closing the quote makes the project quote read-only. Because a closed quote can't be reopened and, before you close a quote, a confirmation dialog will confirm your changes.

If the project quote that is closed as Lost references a project on any of its lines, that project is also marked as Closed. Any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as Won or Lost will not impact that status of the Opportunity, which will remain open until it is manually closed.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
