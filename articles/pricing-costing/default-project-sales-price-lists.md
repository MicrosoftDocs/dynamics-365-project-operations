---
title: Default price lists
description: This article provides information about default sales and cost price lists in Project Operations.
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Default price lists

[!INCLUDE[banner](../includes/banner.md)]

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

Cost price lists don't default to any entity in Project Operations. Determining the cost price list to use for project costs is always done on a per-transaction basis. The system completes the following process to determine which price list to use for project costs:

1. The system looks at the price lists that are attached to the contracting organization unit of the project.
1. Next, the system looks at the date effectivity of the price lists that match the date of the incoming estimate context or actual context.

    - *Estimate context* refers to any of three contexts of estimation in Project Operations:

        - Project estimate line
        - Quote line detail
        - Contract line detail

    - *Actual context* refers to any of three sources for actuals in Project Operations:

       - Entry journal lines that are manually created, or correction journal lines that are created in a correction journal
       - Journal lines that are created during submission of time, expense, or material usage logs
       - Invoice line detail

    When Project Operations matches date effectivity of the incoming journal line or invoice line detail in the *actual context*, it uses the **Transaction date** field.

    - If multiple price lists are effective for the date of the incoming estimate context or actual context, the most recently created price list is selected.
    - If no price lists are attached to the contracting organization unit of the project, the system looks at cost price lists that are attached to project parameters that match the currency of the project.

## Enable multi-currency cost price list

This setting can be found at **Settings** \> **Parameters**. The default value is **No**.

When this setting is enabled (that is, the value is set to **Yes**), the system behaves in the following way:

- It allows cost price lists in any currency to be associated with the organizational unit. For example, a cost price list in the EUR currency can be attached to an organizational unit in the USD currency. The system will continue to validate that cost price lists that are attached to an organizational unit don't have overlapping date effectivity.
- It validates that cost price lists that are attached to project parameters don't have overlapping date effectivity, even if they have different currencies. This behavior differs from the default behavior (that is, the behavior when the value is set to **No**). In the default behavior, only cost price lists that have the **same** currency are validated for non-overlapping date effectivity.
- For an incoming transaction context, it determines the cost price list based on date effectivity only. This behavior differs from the default behavior, where the system selects the cost price list that matches both the currency of the project and date effectivity.

Because of these changes in behavior, Project Operations customers will be able to maintain a global cost price list that will be relevant for the whole company. They won't have to have price lists in each currency of operations. The global price list will have date effectivity and will enable cost rates to be set up in any currency for a specific combination of pricing dimension values. The currency of the cost price list is used only to enter default values when **Role prices**, **Category prices**, and **Price list** item records are created. It won't be used to determine the price list.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
