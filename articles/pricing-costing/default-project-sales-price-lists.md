---
title: Default price lists
description: This topic provides information about default sales and cost price lists in Project Operations.
author: rumant
ms.date: 10/13/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Default price lists

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Sales price lists

Every project quote and contract in Dynamics 365 Project Operations contains a default sales price list. 

### Price list default on project quotes
The system completes the following process to determine which price list to default on a project quote:

1. The system looks at the price lists that are attached to the account's project price lists. 
2. If there are project price lists attached to the account record, the system looks at the sales price lists attached to the project parameters that match the currency of the project quote.
3. Next, the system checks the date effectivity of the price lists that match the date range of the project quote. Specifically, the date the quote was created.
4. If there are multiple price lists that are effective for the date of the project quote, all of the price lists default on the project quote.
5. If no price lists in effect for the date of the project quote, there's no default project price list on the project quote. A warning message will occur on the project quote. The message states that actuals and estimates on the project won't be priced because there are no project price lists attached.

### Price list default on project contracts 
The system completes the following process to determine which price list to default on a project contract:

1. If the contract is created from a quote, the project price lists on the quote are copied over separately and attached to the project contract.
2. If the contract is created from scratch, the system looks at the price lists that are attached to the project price lists of the account. If there aren't project price lists attached to the account record, the system looks for sales price lists attached to the project parameters that match the currency of the project contract.
4. Next, the system checks the date effectivity of the price lists that match the date range of the project contract. Specifically, the date the contract was created.
5. If there are multiple price lists that are effective for the date of the contract, all of the price lists default on the contract.
6. If there are no price lists in effect for the date of the contract, no project price lists default to the contract. A warning message will occur on the project contract. The message states that actuals and estimates on the project won't be priced because there are no project price lists attached.

## Cost price lists

Cost price lists don't default to any entity in Project Operations. Determining the cost price list to use for project costs is always done in the moment. The system completes the following process to determine which price list to use for project costs:

1. The system first looks at the price lists that are attached to the contracting organization unit of the project.
2. The system then looks at the date effectivity of the price lists that match the date of the incoming estimate or actual line. In this situation, *estimate line* refers to all three contexts of estimation in Project Operations:

    - Project estimate line
    - Quote line detail
    - Contract line detail
  
3. If there are multiple price lists that are effective for the date on the incoming estimate or actual, the price list created most recently is selected.
4. If there no price lists attached to the contracting organization unit of the project, the system looks at cost price lists attached to project parameters that match the currency of the project.
5. Next the system looks at the date effectivity of the price lists that match the date of the incoming estimate or actual line. 
6. If there are multiple price lists that are effective for the date on the incoming estimate or actual, the price list created most recently is selected.
7. If there are no cost price lists attached to the project parameters that match the currency and effective date, the system defaults the cost rate to zero (0) on the incoming estimate or actual line.


[!INCLUDE[footer-include](../includes/footer-banner.md)]