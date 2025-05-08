---
title: Close project quotes
description: This article provides information about closing a quote in Project Operations.
author: poojafandan
ms.date: 06/07/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Close project quotes

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A project quote can be closed as **Won** or **Lost**. A draft quote can be closed because the Activate and Revise operations on quotes isn't supported in Microsoft Dynamics 365 Project Operations.

## Close a quote as Won

When you close a project quote as **Won**, the status is set to **Closed**, and the status reason is set to **Won**. Closing the quote makes the project quote read-only and creates a draft project contract that contains the quote information. Because a closed quote can't be reopened, a confirmation dialog box confirms your changes.

If the quote is attached to an opportunity, any other project quotes on the opportunity are automatically closed as **Lost**.

### Financial impact of closing a quote as Won

If there are any actuals for time on a project while it's still attached to a draft quote, only the cost of the time or expense is recorded. 

After a quote is closed as **Won**, the application refactors the costs by reversing the older cost actuals and creating new cost actuals. The application processes these cost actuals based on the billing method of the associated project contract line. If the cost actuals reference a time and material contract line, the corresponding unbilled sales actuals are created when the quote is closed, and the project contract is created. If the cost actuals reference a fixed price contract line, the application stops reprocessing the cost actuals that are based on the split billing rules for the project contract customers.

### Managing how price lists that are attached to the quote are handled during Quote win

When you win a quote in Project Operations, the application provides options that let you specify how price lists are transferred from the quote to the project contract. Three options are available. To access these options, go to **Settings** \> **Parameters**, and open the **Parameters** record. Then, in the **Price List Defaulting Behavior** section, for the **During Contract creation from Quote** setting, select one of the following options.

#### Option 1: Associate quote price lists to Project Contract

Select this option to attach the same price lists on the quote to the project contract. Of the three options, this option has the best performance for Quote win, because only one new record is created from a pricing standpoint. However, if you select this option when a standard price list is used, you expose the contract to any price changes that are made in this price list. Therefore, the prices that were used when the quote was built might deviate from the prices that are used during execution of the project if the prices in the price list are updated after the quote is won. 

#### Option 2: Associate quote price lists to Project Contract with contract-specific price overrides for components estimated on the quote

Select this option to create contract-scoped price overrides for all the components that are estimated in the quote line details. This option creates date-effective price overrides that are scoped to the contract for estimated components (in other words, components that are referenced in the quote line details). Because of these price overrides, price changes in the price list for these components won't affect how the actuals are priced during execution of the project. Because this option doesn't create a full copy of the quote price list, it has better performance than option 3. However, it's slower than option 1 because it leads to the creation of date-effective price overrides for the components that are referenced in the quote line details. Depending on the number of quote line details, Quote win can take longer. If the quote has only a few quote line details, Quote win can be quick.

#### Option 3: Make copies of quote price lists and associate them to Project Contract

Select this option to create a full copy of the quote price list. The name of the contract and the date are appended and attached to this full copy for the project contract. Of the three options, this option has the most impact on the performance of Quote win and the time that is required to create the project contract. This option also causes data explosion of price list records. Therefore, use this option only when you must protect the entire price list (or price lists) that you used during the quote stage for the duration of the project.

## Close a quote as Lost

When you close a project quote as **Lost**, the status is set to **Closed**, and status reason is set to **Lost**. Closing the quote makes the project quote read-only. Because a closed quote can't be reopened, before you close a quote, a confirmation dialog box confirms your changes.

If the project quote that is closed as **Lost** references a project on any of its lines, that project is marked as **Closed**. Any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as **Won** or **Lost** has no impact on the status of the opportunity. The opportunity will remain open until it's manually closed.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
