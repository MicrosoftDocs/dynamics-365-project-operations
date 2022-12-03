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

## Close a quote as Lost

Closing a project quote as Lost will set the status to **Closed** and status reason to **Lost**. Closing the quote makes it read-only. Because a closed quote can't be reopened and, before you close a quote, a confirmation dialog will confirm your changes.

If the project quote that is closed as Lost has a project referenced on any of its lines, that project is also marked as Closed and any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as Won or Lost will not impact that status of the Opportunity, which will remain open until it is manually closed.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
