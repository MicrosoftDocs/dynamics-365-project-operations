---
title: Close a quote
description: This topic provides information about closing quotes in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-project-operations
ms.reviewer: kfend 
ms.author: rumant
---

# Approvals overview

_**Applies To:** Lite deployment - deal to proforma invoicing_

# Close a quote

A project quote can be closed as Won or Lost. The Activate and Revise operations on quotes is not supported in Microsoft Dynamics 365 Project Operations, so a draft quote can be closed.

## Close a quote as Won

Closing a project quote as Won will close the quote with the status set to Closed and the status reason set to Won. Closing the quote makes the project quote read-only and creates a draft project contract that contains the quote information. Because a closed quote can't be reopened, a confirmation dialog There is a confirmation dialog before the changes are done since a closed quote cannot be re-opened and the changes are irreversible.

If the quote is attached to an opportunity, any other project quotes on the opportunity are automatically closed as Lost.

### Financial impact of closing a quote as Won

If there have been any actuals for time recorded on a project while it is still attached to a draft quote, only the cost of the time or expense is recorded. 
After a quote is closed as Won, the application will refactor the costs by reversing the older cost actuals and re-creating new cost actuals. The application will process these cost actuals based on the Billing method of the associated project contract line. If the cost actuals reference a time and material contract line, the system will automatically create corresponding unbilled sales actuals for when the quote is closed and the project contract is created. If the cost actuals reference a fixed price contract line, the application will stop reprocessing the cost actuals based on the split billing rules for the project contract customers.

## Closing a quote as lost:

Closing a project quote as Lost will set the status to Closed and status reason to Lost. This makes the project quote read-only. Because a closed quote can't be reopened and, before you close a quote, a confirmation dialog will confirm your changes.

If the project quote that is closed as Lost has a project referenced on any of its lines, that project is also marked as Closed and any resource bookings from that day forward are canceled.

> [!NOTE]
> In Project Operations, closing a quote as Won or Lost will not impact that status of the Opportunity, which will remain open until it is manually closed.
