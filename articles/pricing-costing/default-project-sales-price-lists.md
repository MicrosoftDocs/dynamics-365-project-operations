---
title: Default price lists
description: This article provides information about default sales and cost price lists in Project Operations.
author: rumant
ms.date: 09/07/2022
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
1. If there are no project price lists attached to the account record, the system looks at the sales price lists attached to the project parameters that match the currency of the project quote.
1. Next, the system checks the date effectivity of the price lists that match the date range of the project quote. Specifically, the date the quote was created.
1. If there are multiple price lists that are effective for the date of the project quote, all of the price lists default on the project quote.
1. If no price lists in effect for the date of the project quote, there's no default project price list on the project quote. A warning message will occur on the project quote. The message states that actuals and estimates on the project won't be priced because there are no project price lists attached.

### Price list default on project contracts 
The system completes the following process to determine which price list to default on a project contract:

1. If the contract is created from a quote, the project price lists on the quote are copied over separately and attached to the project contract.
1. If the contract is created from scratch, the system looks at the price lists that are attached to the project price lists of the account. If there aren't project price lists attached to the account record, the system looks for sales price lists attached to the project parameters that match the currency of the project contract.
1. Next, the system checks the date effectivity of the price lists that match the date range of the project contract. Specifically, the date the contract was created.
1. If there are multiple price lists that are effective for the date of the contract, all of the price lists default on the contract.
1. If there are no price lists in effect for the date of the contract, no project price lists default to the contract. A warning message will occur on the project contract. The message states that actuals and estimates on the project won't be priced because there are no project price lists attached.

## Cost price lists

Cost price lists don't default to any entity in Project Operations. Determining the cost price list to use for project costs is always done on a per transaction basis. The system completes the following process to determine which price list to use for project costs:

1. The system looks at the price lists that are attached to the contracting organization unit of the project.
1. Next, the system looks at the date effectivity of the price lists that match the date of the incoming estimate context or actual context. 
- *Estimate context* refers to any of three contexts of estimation in Project Operations:

    - Project estimate line
    - Quote line detail
    - Contract line detail
  
 - *Actual context* refers to any of three sources for actuals in Project Operations:
   - Entry Journal line created manually, or correction journal lines created on a correction journal.
   - Journal lines created during time, expense, or material usage log submission.
   - Invoice line detail.

- When matching date effectivity of the incoming journal line or invoice line detail in the *actual context*, Project Operations uses the transaction date field.     
    - If there are multiple price lists that are effective for the date on the incoming estimate or actual contexts, the price list created most recently is selected.
    - If there aren't any price lists attached to the contracting organization unit of the project, the application looks at cost price lists attached to project parameters that match the currency of the project.
  
## Enable multi-currency cost price list
This setting can be found in Settings -> Parameters. The default value of this setting is **No**. 
When this setting is enabled or set to **Yes**, the system will: 
1. Allow associating cost price lists in any currency to the Organizational Unit. So you could have a cost price list in EUR currency attached to an Organizational unit whose currency is USD. The system will continue to validate that cost price lists attached to an Organizational Unit don't have overlapping date effectivity.
1. Validate that cost price lists that are attached to Project Parameters don't have overlapping date effectivities even if they have different currencies. This is different from the default behavior when this setting is set to **No** where cost price lists that have the **same** currency are validated for overlapping date effectivities.
1. For an incoming transaction context, determine the cost price list based on date effectivity only. This is different from the default behavior when this setting is set to **No** where the system will select the cost price list that matches the currency on the project AND date effectivity. 

Because of these changes in behaviors, Project Operations customers will be able to maintain a global cost price list that will be relevant for the entire company. It will not be necessary to have price lists in each currency of operations. This global price list will have date effectivity and will allow setup of cost rates in any currency for a for a specific combination of pricing dimension values. The currency on the cost price list is only used for defaulting when creating **Role prices**, **Category prices**, and **Price list** item records, and won't be used to determine the price list. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
