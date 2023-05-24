---
title: Close project-based quotes
description: This article provides information about closing quotes in Project Operations.
author: rumant
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Close project-based quotes

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

A project quote can be closed as **won** or **lost**. 

## Close a quote as Won

Closing a project quote as Won will set the status of the quote to **Closed** and status reason to **Won**. Closing the quotes makes it read-only and creates a draft project contract with all the quote information. Because a closed quote can't be reopened, before you close a quote, a confirmation dialog will confirm your changes.

The project contract created from a project quote is also made available in the Project management and accounting module of Project Operations. If a project contract is not mapped to a project on any of its lines, this project contract is made available as an inactive project contract and becomes active as soon as a project is mapped to at least one of its contract lines.

If the quote is attached to an opportunity, any other project quotes on the opportunity are automatically closed as Lost.

### Financial impact of closing a quote as Won

If there have been any actuals for time recorded on a project while it is still attached to a draft quote, only the cost of the time or expense is recorded. After a quote is closed as Won, the application will refactor the costs by reversing the older cost actuals and re-creating new cost actuals. The application will process these cost actuals based on the Billing method of the associated project contract line. If the cost actuals reference a time and material contract line, the system will automatically create corresponding unbilled sales actuals for when the quote is closed and the project contract is created. If the cost actuals reference a fixed price contract line, the application will stop reprocessing the cost actuals based on the split billing rules for the project contract customers.

All reprocessed actuals are available in the Project management and accounting module for the Project accountant to review, update, and post to the General ledger. 

### Managing how price lists attached to the quote are handled during Quote win

When winning a quote in Project Operations, the application provides options to you on how to transfer Price Lists from Quote to the Project Contract. There are 3 options available. To access these options navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **During Contract creation from Quote**. You will see 3 options:

Option 1 - **Associate quote price lists to project contract**: 
Selecting this option will attach the same price list(s) on the quote to the project contract. Of the 3 options, this option will give the best performance for quote win since there is only one new record that is created from a pricing standpoint. However, selecting this option when a standard price list is used, will expose the contract to any price changes that are made in this price list. So the prices used when building the quote may deviate from the prices used during the execution of the project if prices in the price list got updated after winning the quote. 

Option 2 - **Associate quote price lists to Project Contract with contract-specific price overrides for components estimated on the quote**: 
Selecting this option will create date effective price overrides scoped to the contract only for estimated components i.e. components referenced on quote line details. Due to these price overrides, any price changes in the price list for these components will not impact how the actuals are priced during the execution of the project. This option will not create an entire copy of the quote price list and therefore will give much better performance than selecting Option 3 below. However, it will be slower than Option 1 since it will lead to the creation of Date effective price overrides for components referenced on quote line details. Depending on the number of quote line details, this could take longer to win the quote or be very quick to win the quote if the quote had only a few quote line details.

Option 3 - **Make copies of quote price lists and associate them to Project Contract**: 
Selecting this option will create a full copy of the quote price list with the name of the contract and date appended and attach this full copy to the Project contract. Of the 3 options, this option will have a severe impact on the performance of Quote win and the time it takes to create the project contract. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that was used during quote stage for the duration of the project. 

## Close a quote as Lost

Closing a project quote as Lost will set the status to **Closed** and status reason to **Lost**. Closing the quote makes it read-only. Because a closed quote can't be reopened and, before you close a quote, a confirmation dialog will confirm your changes.

If the project quote that is closed as Lost has a project referenced on any of its lines, that project is also marked as Closed and any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as Won or Lost will not impact that status of the Opportunity, which will remain open until it is manually closed.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
