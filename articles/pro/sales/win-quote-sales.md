---
title: Close project quotes
description: This article provides information about closing a quote in Project Operations.
author: rumant
ms.date: 10/01/2020
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

## Closing a quote as lost

When you close a project quote as Lost, the status is set to Closed and status reason is Lost. Closing the quote makes the project quote read-only. Because a closed quote can't be reopened and, before you close a quote, a confirmation dialog will confirm your changes.

If the project quote that is closed as Lost references a project on any of its lines, that project is also marked as Closed. Any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as Won or Lost will not impact that status of the Opportunity, which will remain open until it is manually closed.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
