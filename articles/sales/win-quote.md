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

When you close a project quote as Won, the status is set to **Closed**, and the status reason is set to **Won**. Closing the quote makes the project quote read-only and creates a draft project contract that contains the quote information. Because a closed quote can't be reopened, a confirmation dialog confirms your changes.

The project contract created from a project quote is also made available in the Project management and accounting module of Project Operations. If a project contract isn't mapped to a project on any of its lines, this project contract is made available as an inactive project contract and becomes active as soon as a project is mapped to at least one of its contract lines.

If the quote is attached to an opportunity, any other project quotes on the opportunity are automatically closed as **Lost**.

### Financial impact of closing a quote as Won

If there have been any actuals for time recorded on a project while it's still attached to a draft quote, only the cost of the time or expense is recorded. After a quote is closed as Won, the application will refactor the costs by reversing the older cost actuals and re-creating new cost actuals. The application will process these cost actuals based on the Billing method of the associated project contract line. If the cost actuals reference a time and material contract line, the system will automatically create corresponding unbilled sales actuals for when the quote is closed and the project contract is created. If the cost actuals reference a fixed price contract line, the application will stop reprocessing the cost actuals based on the split billing rules for the project contract customers.

All reprocessed actuals are available in the Project management and accounting module for the Project accountant to review, update, and post to the General ledger. 

### Managing how price lists attached to the quote are handled during Quote win

If there are any actuals for time on a project while i's still attached to a draft quote, only the cost of the time or expense is recorded. 

After a quote is closed as **Won**, the application refactors the costs by reversing the older cost actuals and re-creating new cost actuals. The application processes these cost actuals based on the Billing method of the associated project contract line. If the cost actuals reference a time and material contract line, the corresponding unbilled sales actuals are created when the quote is closed, and the project contract is created. If the cost actuals reference a fixed price contract line, the application stops reprocessing the cost actuals that are based on the split billing rules for the project contract customers.

### Managing how price lists are attached to the quote are handled during Quote win

When you win a quote in Project Operations, the application provides options to you on how to transfer Price Lists from Quote to the Project Contract. There are three options available. To access these options, navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **During Contract creation from Quote**. You see three options:

#### Option 1 - Associate quote price lists to Project Contract

Selecting this option attaches the same price list(s) on the quote to the Project contract. Of the three options, this option has the best performance for Quote win because there's only one new record that's created from a pricing standpoint. However, selecting this option when a standard price list is used exposes the contract to any price changes that are made in this price list. So, the prices used when building the quote may deviate from the prices used during the execution of the project if prices in the price list are update after winning the quote. 

#### Option 2 - Associate quote price lists to Project Contract with contract-specific price overrides for components estimated on the quote

Selecting this option creates contract-scoped price overrides for all the components estimated on the Quote line details. This option creates date-effective price overrides that are scoped to the contract for estimated components. In other words, components referenced on the quote line details. Due to these price overrides, any price changes in the price list for these components won't impact how the actuals are priced during the execution of the project. This option won't create an entire copy of the quote price list and therefore has better performance than selecting Option three below. However, it's slower than Option one because it leads to the creation of date-effective price overrides for the components references on the quote line details. Depending on the number of quote line details, it can take longer to win the quote or be quick to win the quote if the Quote only has a few Quote line details.

#### Option 3 - Make copies of quote price lists and associate them to Project Contract
Selecting this option creates a full copy of the quote price list. The name of the contract and the date are appended, and attached to this full copy to the Project contract. Of the three options, this option has a severe impact on the performance of Quote win and the time it takes to create the Project Contract. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that was used during quote stage for the duration of the Project. 

## Close a quote as Lost

When you close a project quote as lost, the status is set to **Closed**, and status reason is set to **Lost**. Closing the quote makes the project quote read-only. Because a closed quote can't be reopened, before you close a quote, a confirmation dialog confirms your changes.

If the project quote that is closed as **Lost** references a project on any of its lines, that project is also marked as **Closed**. Any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as **Won** or **Lost** won't impact that status of the opportunity, which will remain open until it's manually closed.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
